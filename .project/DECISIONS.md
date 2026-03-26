# WgSocket.net — Architectural Decisions

Decisions recorded as lightweight ADRs (Architectural Decision Records).

## ADR-001: WireGuard Protocol Over ZeroTier

- **Date:** 2026-03-26
- **Status:** Accepted
- **Context:** Evaluated ZeroTier for overlay networking across Biztactix/Helpdesk infrastructure. ZeroTier's `libzt` has an in-process socket API, but ZSSP is single-threaded, code is BSL-1.1 licensed, and the ecosystem is tied to proprietary infrastructure. WireGuard-based solutions dominate on throughput, multi-threading, and open licensing — but none provide an in-process .NET socket API.
- **Decision:** Build on WireGuard using boringtun (Cloudflare's Rust implementation, BSD-3) rather than wrapping ZeroTier.
- **Consequences:**
  - Full multi-threaded throughput (WireGuard is not single-threaded like ZeroTier's ZSSP)
  - BSD-3 + MIT licence stack — genuinely open source
  - Interoperable with every WireGuard implementation
  - No Layer 2 (Ethernet bridging) — WireGuard is Layer 3 only
  - No built-in peer discovery or NAT traversal — requires a STUN/TURN layer or control plane (NetBird/Headscale) if needed

## ADR-002: smoltcp for Userspace TCP/IP Over lwIP or gVisor Netstack

- **Date:** 2026-03-26
- **Status:** Accepted
- **Context:** Need a full userspace TCP/IP stack. Three options: lwIP (C, used by ZeroTier), gVisor netstack (Go, used by Tailscale), smoltcp (Rust). Since boringtun is already Rust, a Rust TCP/IP stack avoids cross-language linking.
- **Decision:** Use smoltcp as the userspace TCP/IP stack.
- **Consequences:**
  - Single Rust toolchain — no C build system or CGo complexity
  - smoltcp's sans-I/O design fits naturally with boringtun's decrypt output
  - Proven by `wireguard_netstack` and `onetun` crates
  - ~Gbps throughput in loopback tests
  - Smaller feature set than lwIP (no DHCP client, limited multicast) — acceptable for static WireGuard configs

## ADR-003: Rust Glue Crate with C ABI Over Direct C# Unsafe Code

- **Date:** 2026-03-26
- **Status:** Accepted
- **Context:** The boringtun + smoltcp + poll loop composition needs a home. Options: (a) Rust crate with simple C ABI, (b) expose both individually via C FFI and orchestrate from C# unsafe, (c) rewrite in C#.
- **Decision:** Thin Rust crate (~200-400 lines) composing boringtun and smoltcp internally, exporting high-level C ABI. C# sees only simple function calls.
- **Consequences:**
  - Narrow FFI boundary — opaque handles, byte buffers, integer return codes
  - All unsafe memory management stays in Rust with borrow checker guardrails
  - C# layer is ~300 lines of straightforward P/Invoke wrapper
  - Cross-FFI debugging requires both toolchains
  - Small enough to audit or fuzz thoroughly

## ADR-004: System.Net.Sockets-Compatible API Surface

- **Date:** 2026-03-26
- **Status:** Accepted
- **Context:** Primary value prop is minimal code changes for existing .NET code. Options: (a) mirror `System.Net.Sockets.Socket` signatures, (b) new idiomatic API, (c) custom `SocketsHttpHandler`.
- **Decision:** Mirror `System.Net.Sockets.Socket` — same method names (`Connect`, `Bind`, `Listen`, `Accept`, `Send`, `Receive`), same shapes. Class is `WgSocket.Socket` (separate namespace, not a subclass).
- **Consequences:**
  - Near-drop-in replacement — change `using` + type declaration only
  - Cannot inherit from `System.Net.Sockets.Socket` (sealed/coupled to OS handles)
  - Should provide `WgSocket.NetworkStream` for Stream-based consumers
  - Async variants (`SendAsync`, `ReceiveAsync`, `ConnectAsync`) required from the start

## ADR-005: NuGet Package with Embedded Native Binaries

- **Date:** 2026-03-26
- **Status:** Accepted
- **Context:** Native Rust cdylib must be distributed with C# assembly. Options: (a) embed in NuGet via `runtimes/{rid}/native/`, (b) separate native install, (c) dotnet tool.
- **Decision:** Single NuGet package with C# assembly + pre-built natives for win-x64, linux-x64, osx-x64, osx-arm64.
- **Consequences:**
  - `dotnet add package WgSocket` is the only step
  - Package ~8-16MB (4 native binaries) — acceptable
  - Missing platforms fail with clear `DllNotFoundException` — add targets later by demand
  - CI must cross-compile for all four targets on every release

## ADR-006: No Built-In Control Plane or Peer Discovery

- **Date:** 2026-03-26
- **Status:** Accepted
- **Context:** WireGuard requires pre-configured endpoints. Including a control plane would expand scope significantly.
- **Decision:** Transport library only. Accepts WireGuard config (keys, endpoints, allowed IPs), provides sockets. Peer discovery, key distribution, NAT traversal, ACL management are out of scope.
- **Consequences:**
  - Small, auditable, single-purpose library
  - Consumers needing dynamic discovery must layer it on top (Headscale/NetBird for control plane, WgSocket for data plane)
  - Works best for known-topology scenarios
  - Future companion package (`WgSocket.Discovery`) could add STUN/TURN without bloating core