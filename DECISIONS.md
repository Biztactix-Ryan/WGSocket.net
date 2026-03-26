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

## ADR-003: Rust Glue Crate with C ABI + csbindgen Auto-Generated Bindings

- **Date:** 2026-03-26
- **Status:** Accepted
- **Context:** The composition of boringtun + smoltcp + poll loop + socket buffer management needs to live somewhere. Options: (a) a Rust crate that does all the wiring and exposes a simple C ABI (`wg_connect`, `wg_send`, etc.), (b) expose boringtun and smoltcp individually via C FFI and orchestrate them from C# unsafe code, (c) rewrite one or both components in C#. Additionally, keeping the C# P/Invoke declarations in sync with the Rust exports is a maintenance burden — hand-writing `NativeMethods.cs` is error-prone and drifts over time.
- **Decision:** Build a thin Rust crate (~200-400 lines) that composes boringtun and smoltcp internally and exports a high-level C ABI. Use **csbindgen** (Cysharp) to auto-generate the C# `LibraryImport` declarations directly from the Rust `extern "C"` functions at build time. The C# side never hand-writes P/Invoke signatures — `NativeMethods.g.cs` is a generated file.
- **Consequences:**
  - The FFI boundary is narrow and simple — opaque handles, byte buffers, integer return codes
  - All unsafe memory management (raw pointers, buffer lifetimes) stays in Rust where the borrow checker provides guardrails
  - The auto-generated bindings eliminate an entire class of bugs (signature mismatch, incorrect marshalling attributes, stale declarations)
  - The C# layer is ~300 lines of managed wrapper around the generated native methods — minimal unsafe C# code
  - Debugging across the FFI boundary is harder than pure-C# or pure-Rust — requires familiarity with both toolchains
  - The Rust crate is the single novel security-critical component — small enough to audit or fuzz thoroughly
  - In NativeAOT mode with `DirectPInvoke`, the generated `LibraryImport` calls compile to direct native function calls with zero overhead (see ADR-007)

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

## ADR-005: Dual-Mode NuGet Package (Static Libs for AOT + Shared Libs for JIT)

- **Date:** 2026-03-26
- **Status:** Accepted (supersedes original shared-only approach)
- **Context:** The library has a native Rust component that must be distributed alongside the managed C# assembly. NativeAOT consumers benefit from static linking (single binary, no DLL loading, direct function calls). JIT consumers (`dotnet run`, standard publish) need shared libraries loaded at runtime. Shipping both in one NuGet package serves both use cases from a single `dotnet add package` step.
- **Decision:** Ship a single NuGet package containing the C# assembly, **static libraries** (`.a`/`.lib`) for NativeAOT consumers, and **shared libraries** (`.dll`/`.so`/`.dylib`) for JIT consumers, for all four target platforms (`win-x64`, `linux-x64`, `osx-x64`, `osx-arm64`). The `.csproj` conditionally wires `<DirectPInvoke>` + `<NativeLibrary>` when `PublishAot=true`; JIT consumers use standard runtime library resolution with no extra config.
- **Consequences:**
  - `dotnet add package WgSocket` is still the only step for consumers — works for both AOT and JIT
  - Package size roughly doubles compared to shared-only (~4-8MB of static libs added on top of ~8-16MB of shared libs) — acceptable given the value proposition
  - The Rust crate's `Cargo.toml` specifies `crate-type = ["staticlib", "cdylib"]` — both outputs from one `cargo build`
  - CI must produce 8 native artefacts (4 targets × 2 crate types) per release
  - Platforms not included will fail at runtime with a clear error — additional targets added based on demand
  - If NativeAOT static linking proves problematic on a specific platform (e.g. linker symbol conflicts, platform-specific AOT bugs), that platform falls back to the shared library path gracefully — the consumer just doesn't set `PublishAot=true` for that target

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

## ADR-007: NativeAOT Static Linking as Primary Target, Shared Library as Fallback

- **Date:** 2026-03-26
- **Status:** Accepted
- **Context:** The original design assumed a conventional shared-library P/Invoke approach — Rust compiles to a `.so`/`.dll`/`.dylib`, .NET loads it at runtime, function calls cross a marshalling boundary. This works but has drawbacks: separate native files to deploy, runtime library loading overhead, and a visible FFI seam in the architecture. .NET 8+ NativeAOT supports `<DirectPInvoke>` with `<NativeLibrary>`, which statically links a native `.a`/`.lib` directly into the published binary. At that point, P/Invoke annotations compile to direct native function calls — the Rust and C# code fuse into one executable with no FFI overhead at the binary level.
- **Decision:** Target NativeAOT static linking as the primary integration mode. Build the Rust crate as both `staticlib` and `cdylib`. Design all C# interop using `LibraryImport` (which works identically in both modes). The shared library path is maintained as a fully functional fallback for JIT execution and for any platform where NativeAOT static linking proves problematic.
- **Consequences:**
  - Primary path: single-file deployment, zero interop overhead, no DLL management — the "it just works" experience for AOT consumers
  - The shared library fallback means the project is never blocked by NativeAOT issues — if static linking breaks on a specific platform/version, consumers just publish without AOT and everything still works
  - Both modes use identical C# source code (same `LibraryImport` declarations, auto-generated by csbindgen) — no conditional compilation or separate code paths
  - NativeAOT static linking with Rust is well-trodden (many NuGet packages with native deps do this) but edge cases exist: symbol name collisions if the consumer links other Rust static libs, platform-specific linker quirks on macOS, potential issues with Rust's allocator conflicting with .NET's
  - The project should validate NativeAOT static linking on all four target platforms early (Sprint 1 milestone) — if any platform fails, that platform uses the shared library path and the issue is logged for investigation, not treated as a blocker

### Fallback Escalation Ladder

If NativeAOT static linking encounters problems, the fallback strategy is tiered:

1. **Platform-specific fallback** — If static linking fails on one platform (e.g. macOS linker issues), that platform uses the shared library while others stay on static. No code changes needed.
2. **Full shared-library mode** — If static linking proves unreliable across multiple platforms, drop the static libs from the NuGet package entirely. The architecture is unchanged; consumers just don't get single-file deployment. This is what the original design assumed and it's proven technology.
3. **Function pointer mode** — If `LibraryImport` P/Invoke has issues in a specific scenario, raw `delegate* unmanaged` function pointers via `NativeLibrary.GetExport()` can replace it. Near-zero overhead, bypasses the P/Invoke machinery entirely. More code to write but fully manual control.
4. **Pure C# WireGuard implementation** — Nuclear option. Replace boringtun with a C# Noise Protocol implementation (Noise.NET + `System.Security.Cryptography`). Keep smoltcp via FFI for the TCP/IP stack only (or accept significantly more work to reimplement TCP in managed code). Eliminates the native dependency entirely but puts the WireGuard implementation's correctness on us rather than Cloudflare. Only pursue this if the Rust FFI approach proves fundamentally unworkable, which is unlikely given the widespread use of native interop in the .NET ecosystem.

Each tier is a clean fallback — the API surface (`WgSocket.Socket`) never changes regardless of which interop strategy is used underneath. The consumer's code is always just `new WgSocket.Socket(...)` with no awareness of the plumbing.
