# Architectural Decisions — WgSocket

Decisions are recorded as lightweight ADRs (Architectural Decision Records).

## ADR-001: WireGuard Protocol Over ZeroTier

- **Date:** 2026-03-26
- **Status:** Accepted
- **Context:** The project originated from evaluating ZeroTier for overlay networking across Biztactix/Helpdesk infrastructure. ZeroTier's `libzt` offers a compelling in-process socket API via its NuGet package (`ZeroTier.Sockets`), but the underlying protocol (ZSSP) is single-threaded, the code is BSL-1.1 licensed (not true open source), and the ecosystem is tied to ZeroTier Inc's proprietary planet/Central infrastructure. A comparison of ZeroTier, Tailscale, Nebula, NetBird, Netmaker, and Headscale revealed that WireGuard-based solutions dominate on throughput, multi-threading, and open licensing — but none provide an in-process .NET socket API.
- **Decision:** Build on the WireGuard protocol using boringtun (Cloudflare's Rust implementation, BSD-3 licensed) rather than wrapping ZeroTier's libzt or forking ZeroTier's custom protocol.
- **Consequences:**
  - Full multi-threaded throughput potential (WireGuard is not single-threaded like ZeroTier's ZSSP)
  - BSD-3 + MIT licence stack — genuinely open source, no BSL restrictions
  - Interoperable with every WireGuard implementation (kernel, wireguard-go, other boringtun users)
  - No Layer 2 (Ethernet bridging) support — WireGuard is Layer 3 only. ZeroTier's L2 bridging is genuinely hard to replace; if L2 is needed, it must be handled separately.
  - No built-in peer discovery or NAT traversal coordination — WireGuard requires endpoints to be configured. A STUN/TURN layer or a control plane like NetBird/Headscale would need to be layered on top if dynamic NAT traversal is required.

## ADR-002: smoltcp for Userspace TCP/IP Over lwIP or gVisor Netstack

- **Date:** 2026-03-26
- **Status:** Accepted
- **Context:** An in-process socket API requires a full userspace TCP/IP stack (TCP state machine, IP routing, socket buffer management) that operates on raw frames without any OS kernel involvement. Three viable options exist: lwIP (C, used by ZeroTier's libzt), gVisor netstack (Go, used by Tailscale's tsnet), and smoltcp (Rust). Since the crypto layer (boringtun) is already in Rust, using a Rust TCP/IP stack avoids cross-language linking complexity and keeps the entire native layer in one toolchain.
- **Decision:** Use smoltcp as the userspace TCP/IP stack.
- **Consequences:**
  - Single Rust toolchain for the entire native layer — no C build system (lwIP) or CGo complexity (gVisor)
  - smoltcp's sans-I/O design is a natural fit for feeding frames from boringtun's decrypt output
  - The `wireguard_netstack` and `onetun` crates demonstrate that the boringtun + smoltcp composition works in practice
  - smoltcp achieves ~Gbps throughput in loopback tests — adequate for the target use cases
  - smoltcp has a smaller feature set than lwIP (no DHCP client, limited multicast) — acceptable for an overlay network where IPs are statically configured via WireGuard config
  - smoltcp has a C FFI crate (`smoltcp-c`) that could also be used independently, but integrating at the Rust level is cleaner

## ADR-003: Rust Glue Crate with C ABI Over Direct C# Unsafe Code

- **Date:** 2026-03-26
- **Status:** Accepted
- **Context:** The composition of boringtun + smoltcp + poll loop + socket buffer management needs to live somewhere. Options: (a) a Rust crate that does all the wiring and exposes a simple C ABI (`wg_connect`, `wg_send`, etc.), (b) expose boringtun and smoltcp individually via C FFI and orchestrate them from C# unsafe code, (c) rewrite one or both components in C#.
- **Decision:** Build a thin Rust crate (~200-400 lines) that composes boringtun and smoltcp internally and exports a high-level C ABI. The C# side only sees simple function calls, not the internal composition.
- **Consequences:**
  - The FFI boundary is narrow and simple — opaque handles, byte buffers, integer return codes. Easy to get right in P/Invoke.
  - All unsafe memory management (raw pointers, buffer lifetimes) stays in Rust where the borrow checker provides guardrails
  - The C# layer is ~300 lines of straightforward P/Invoke + managed wrapper — minimal unsafe C# code
  - Debugging across the FFI boundary is harder than pure-C# or pure-Rust — requires familiarity with both toolchains
  - The Rust crate is the single novel security-critical component — small enough to audit or fuzz thoroughly

## ADR-004: System.Net.Sockets-Compatible API Surface

- **Date:** 2026-03-26
- **Status:** Accepted
- **Context:** The primary value proposition of the library is that existing .NET code can switch to WireGuard overlay networking with minimal code changes. The API should feel native to .NET developers. Options: (a) mirror `System.Net.Sockets.Socket` method signatures exactly, (b) design a new idiomatic API (e.g. `Stream`-based), (c) implement `System.Net.Sockets.Socket` via a custom `SocketsHttpHandler` or similar.
- **Decision:** Mirror the `System.Net.Sockets.Socket` API — same method names (`Connect`, `Bind`, `Listen`, `Accept`, `Send`, `Receive`), same parameter shapes, same return types. The class is `WgSocket.Socket` in a separate namespace, not a subclass of `System.Net.Sockets.Socket`.
- **Consequences:**
  - Near-drop-in replacement — consumers change the `using` / type declaration and nothing else
  - Cannot literally inherit from `System.Net.Sockets.Socket` (it's sealed in many paths and tightly coupled to OS handles) — so code using `Socket` as a parameter type needs to be updated to use the WgSocket type or an interface
  - Should also provide `WgSocket.NetworkStream` wrapping the socket for `Stream`-based consumers (ASP.NET Core Kestrel, HttpClient, etc.)
  - Async variants (`SendAsync`, `ReceiveAsync`, `ConnectAsync`) are expected and should be implemented from the start — async is the default in modern .NET

## ADR-005: NuGet Package with Embedded Native Binaries

- **Date:** 2026-03-26
- **Status:** Accepted
- **Context:** The library has a native component (the Rust cdylib) that must be distributed alongside the managed C# assembly. Options: (a) embed natives in the NuGet package using `runtimes/{rid}/native/` conventions, (b) require consumers to install the native library separately, (c) distribute as a dotnet tool that manages its own binaries.
- **Decision:** Ship a single NuGet package containing the C# assembly and pre-built native binaries for `win-x64`, `linux-x64`, `osx-x64`, and `osx-arm64`. The .NET runtime's native library resolution handles loading the correct binary for the current platform.
- **Consequences:**
  - `dotnet add package WgSocket` is the only step for consumers — no separate native install
  - The NuGet package will be larger than a pure-C# library (~2-4MB per native binary × 4 targets = ~8-16MB total) — acceptable for a networking library
  - Platforms not included (e.g. `linux-arm64`, `win-arm64`) will fail at runtime with a clear `DllNotFoundException` — additional targets can be added later based on demand
  - CI must cross-compile for all four targets on every release — adds build complexity but ensures all binaries are always in sync

## ADR-006: No Built-In Control Plane or Peer Discovery

- **Date:** 2026-03-26
- **Status:** Accepted
- **Context:** WireGuard requires peers to know each other's public keys and endpoints in advance. Solutions like Tailscale (Headscale), NetBird, and ZeroTier Central provide control planes that handle key distribution, peer discovery, and NAT traversal coordination. Including a control plane in WgSocket would significantly expand scope and couple the library to specific infrastructure.
- **Decision:** WgSocket is a transport library only. It accepts a WireGuard configuration (keys, endpoints, allowed IPs) and provides sockets. Peer discovery, key distribution, NAT traversal coordination (STUN/TURN), and ACL management are explicitly out of scope.
- **Consequences:**
  - The library remains small, auditable, and single-purpose
  - Consumers who need dynamic peer discovery must layer it on top (e.g. use Headscale/NetBird for the control plane, WgSocket for the in-process data plane)
  - Static endpoint configuration means the library works best for known-topology scenarios (e.g. connecting to a fixed set of servers) rather than fully dynamic mesh networking
  - A future companion package (`WgSocket.Discovery` or similar) could add STUN/TURN support without bloating the core library
