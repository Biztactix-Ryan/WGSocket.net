# WgSocket

## Overview

WgSocket is a .NET library that provides a `System.Net.Sockets.Socket`-compatible API for WireGuard overlay networking, running entirely in userspace with no daemon, no TUN adapter, and no elevated privileges. It composes Cloudflare's **boringtun** (WireGuard protocol implementation in Rust, BSD-3 licensed) with **smoltcp** (a freestanding TCP/IP stack in Rust, MIT licensed) via a thin Rust glue crate exposing a C ABI, which is then consumed from C# via P/Invoke. The result is a NuGet package that lets any .NET application join a WireGuard network by swapping `System.Net.Sockets.Socket` for `WgSocket.Socket` — a one-line type change.

Nothing equivalent exists on NuGet today. The closest prior art is ZeroTier's `libzt` (which bundles lwIP + ZeroTier's custom protocol), but that is BSL-licensed, single-threaded, and tied to ZeroTier's proprietary overlay. WgSocket is fully open source, uses the widely-audited WireGuard protocol, and leverages WireGuard's multi-threaded design.

## Goals

- Deliver a NuGet package (`WgSocket`) targeting .NET 8+ that provides in-process WireGuard connectivity with zero OS-level dependencies beyond a single UDP socket
- Mirror the `System.Net.Sockets.Socket` API surface closely enough that existing socket code can switch with a type change — `Bind()`, `Listen()`, `Accept()`, `Connect()`, `Send()`, `Receive()` must all work with familiar signatures
- Ship native binaries for `win-x64`, `linux-x64`, `osx-x64`, and `osx-arm64` inside the NuGet package using standard `runtimes/` directory conventions
- Achieve throughput competitive with WireGuard kernel module on single-stream workloads (the bottleneck will be smoltcp's TCP implementation, not the crypto)
- Maintain a fully open-source licence stack — BSD-3 (boringtun) + MIT (smoltcp) + project licence (MIT or Apache-2 TBD)
- Keep the novel code surface small: ~200-400 lines of Rust glue, ~300 lines of C# P/Invoke wrapper — minimise the attack surface and maintenance burden

## Team

- **Ryan Tregea** — Sole developer. 20+ years IT experience, .NET / ASP.NET Core / Hangfire stack, self-hosted infrastructure. Primary consumer of the library through Biztactix/Helpdesk projects (Claude Orchestrator, ProjectMan, client infrastructure tooling).
- Potential contributor: **Harry** (colleague, identified as secondary user for related tooling)

## Repository Structure

```
WgSocket/
├── .project/                    # ProjectMan system-context docs (these files)
├── src/
│   ├── wgsocket-native/         # Rust crate: boringtun + smoltcp glue + C ABI
│   │   ├── Cargo.toml           # crate-type = ["staticlib", "cdylib"]
│   │   ├── build.rs             # csbindgen integration — generates NativeMethods.g.cs
│   │   ├── src/
│   │   │   ├── lib.rs           # C FFI exports: wg_connect, wg_send, wg_recv, etc.
│   │   │   ├── tunnel.rs        # boringtun ↔ smoltcp wiring
│   │   │   └── config.rs        # WireGuard config parsing (wg.conf format)
│   │   └── generated/           # csbindgen output checked in for CI drift detection
│   │       └── NativeMethods.g.cs
│   ├── WgSocket/                # C# class library (.NET 8+)
│   │   ├── WgSocket.csproj
│   │   ├── Socket.cs            # Main WgSocket.Socket class (managed wrapper)
│   │   ├── WgDevice.cs          # Device/tunnel lifecycle management
│   │   ├── WgPeer.cs            # Peer configuration model
│   │   └── NativeMethods.g.cs   # ← symlink/copy from Rust generated/ (auto-generated, do not hand-edit)
│   └── WgSocket.Tests/          # xUnit test project
│       └── WgSocket.Tests.csproj
├── native/                      # Pre-built native binaries (CI output)
│   ├── win-x64/                 # Contains both .lib (static) and .dll (shared)
│   ├── linux-x64/               # Contains both .a (static) and .so (shared)
│   ├── osx-x64/                 # Contains both .a (static) and .dylib (shared)
│   └── osx-arm64/               # Contains both .a (static) and .dylib (shared)
├── samples/
│   ├── EchoServer/              # Simple TCP echo server using WgSocket (AOT-published)
│   └── ChatClient/              # P2P chat example
├── build/                       # CI/CD scripts, cross-compilation tooling
├── README.md
├── LICENSE
└── WgSocket.sln
```

## Conventions

- **Rust:** Follow standard `cargo fmt` / `cargo clippy` conventions. The Rust crate is a `cdylib` targeting C ABI — no Rust-specific types cross the FFI boundary.
- **C#:** Follow .NET coding conventions. Target `net8.0` minimum. Use `LibraryImport` (source-generated P/Invoke) over legacy `DllImport` where possible for AOT compatibility.
- **Branching:** `main` is the release branch. Feature branches named `feature/{short-description}`. Use conventional commits (`feat:`, `fix:`, `chore:`, `docs:`).
- **Testing:** Rust side tested with `cargo test` (unit tests for packet composition, integration tests using loopback). C# side tested with xUnit. CI must pass both before merge.
- **Versioning:** SemVer. The NuGet package version and Rust crate version are kept in sync.

## Status

**Greenfield — Design phase.** The architecture is defined and the core composition (boringtun + smoltcp) has been validated by existing projects (onetun, wireguard_netstack). No code written yet. The project is ready for task breakdown and initial implementation.
