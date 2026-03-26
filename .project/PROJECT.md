# WgSocket.net

A .NET library providing a `System.Net.Sockets.Socket`-compatible API for WireGuard overlay networking, running entirely in userspace with no daemon, no TUN adapter, and no elevated privileges. Composes Cloudflare's **boringtun** (WireGuard protocol, BSD-3) with **smoltcp** (userspace TCP/IP stack, MIT) via a thin Rust glue crate exposing a C ABI, consumed from C# via P/Invoke.

## Architecture

### Tech Stack

- **Language**: C# (.NET 8+) + Rust
- **Framework**: .NET 8+ (class library / NuGet package)
- **Database**: None (library, not a service)
- **Key Libraries**:
  - **boringtun** (Rust, BSD-3) — Cloudflare's WireGuard protocol implementation (Noise_IKpsk2 handshake, ChaCha20-Poly1305 encryption)
  - **smoltcp** (Rust, MIT) — Freestanding userspace TCP/IP stack (TCP state machine, IP routing, socket buffers)
  - **cbindgen** (Rust tool) — C header generation from Rust exports
  - **System.Runtime.InteropServices** — LibraryImport / source-generated P/Invoke (AOT-compatible)

### Components

- **wgsocket-native** (`src/wgsocket-native/`) — Rust cdylib crate (~200-400 lines) composing boringtun + smoltcp, exposing C ABI functions: `wg_device_new`, `wg_connect`, `wg_listen`, `wg_accept`, `wg_send`, `wg_recv`, `wg_close`, `wg_device_free`
- **WgSocket** (`src/WgSocket/`) — C# class library (~300 lines) wrapping native calls via P/Invoke. Main classes: `Socket` (System.Net.Sockets-compatible API), `WgDevice` (tunnel lifecycle), `WgPeer` (peer config), `NativeMethods` (P/Invoke declarations)
- **WgSocket.Tests** (`src/WgSocket.Tests/`) — xUnit test project

### Data Flow

**Outbound:** `Socket.Send()` → P/Invoke → `wg_send` → smoltcp segments/headers → boringtun encrypts → real UDP socket sends to peer

**Inbound:** Real UDP socket receives → boringtun decrypts → smoltcp processes TCP/IP → `wg_recv` → P/Invoke → `Socket.Receive()` returns data

**Handshake:** On first contact, boringtun initiates Noise_IKpsk2 handshake via real UDP socket. Rekeys every 2 min / 2^64 bytes per WireGuard spec.

The Rust glue runs a poll loop on a dedicated thread per `WgDevice`, shuttling packets between boringtun and smoltcp's sans-I/O interface.

## Key Decisions

- **WireGuard over ZeroTier** — Multi-threaded, BSD-3 licensed, interoperable with all WireGuard implementations. ZeroTier's ZSSP is single-threaded and BSL-licensed. (ADR-001, 2026-03-26)
- **smoltcp over lwIP/gVisor netstack** — Single Rust toolchain, no C/CGo complexity. Proven by onetun and wireguard_netstack crates. (ADR-002, 2026-03-26)
- **Rust glue crate with C ABI** — Narrow FFI boundary (opaque handles, byte buffers, error codes). All unsafe stays in Rust with borrow checker guardrails. (ADR-003, 2026-03-26)
- **System.Net.Sockets-compatible API** — Near-drop-in replacement. Change `using` + type declaration, everything else stays the same. (ADR-004, 2026-03-26)
- **NuGet with embedded native binaries** — `dotnet add package WgSocket` is the only install step. ~8-16MB package with 4 platform targets. (ADR-005, 2026-03-26)
- **No built-in control plane** — Transport only. Peer discovery, key distribution, NAT traversal are consumer's responsibility. (ADR-006, 2026-03-26)

## Dependencies

| Dependency | Purpose | Licence |
|---|---|---|
| **boringtun** (Rust crate) | WireGuard protocol — handshake, encryption, anti-replay | BSD-3-Clause |
| **smoltcp** (Rust crate) | Userspace TCP/IP — TCP state machine, IP routing | MIT |
| **cbindgen** (Rust tool) | C header generation from `extern "C"` exports | MPL-2.0 |
| **System.Runtime.InteropServices** (in-box) | LibraryImport / P/Invoke | .NET SDK |

No third-party NuGet dependencies in the core library (zero transitive deps by design).

## Development Setup

**Prerequisites:**
- .NET 8+ SDK
- Rust toolchain (stable) via `rustup`
- Cross-compilation targets: `rustup target add x86_64-pc-windows-msvc x86_64-unknown-linux-gnu x86_64-apple-darwin aarch64-apple-darwin`

**Build:**
```bash
# Rust native library
cd src/wgsocket-native && cargo build --release

# C# library + tests
dotnet build
dotnet test
```

**Conventions:**
- Rust: `cargo fmt` + `cargo clippy` (warnings are errors in CI)
- C#: .NET coding conventions, `LibraryImport` over `DllImport`
- Branching: `main` = release, `feature/{description}` for features
- Commits: conventional commits (`feat:`, `fix:`, `chore:`, `docs:`)
- Versioning: SemVer, NuGet + Cargo versions kept in sync

## Repository Structure

```
WgSocket/
├── .project/                    # ProjectMan system-context docs
├── src/
│   ├── wgsocket-native/         # Rust crate: boringtun + smoltcp glue + C ABI
│   ├── WgSocket/                # C# class library (.NET 8+)
│   └── WgSocket.Tests/          # xUnit test project
├── native/                      # Pre-built native binaries (CI output)
├── samples/
│   ├── EchoServer/              # TCP echo server example
│   └── ChatClient/              # P2P chat example
├── build/                       # CI/CD scripts
└── WgSocket.sln
```

## Team

- **Ryan Tregea** — Sole developer. 20+ years IT, .NET / ASP.NET Core / Hangfire stack.
- **Harry** — Potential contributor (colleague, secondary user)

---
*Last reviewed: 2026-03-26*
*Update this document when architecture changes. The daily audit checks for staleness.*
