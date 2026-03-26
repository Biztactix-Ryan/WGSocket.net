# WgSocket.net — Vision

## Problem

No NuGet package exists today that lets a .NET application join a WireGuard network in-process. Current options:

- **System-level WireGuard** (kernel module, wireguard-go) — requires elevated privileges, a TUN adapter, and a separate daemon. Not embeddable in application code.
- **ZeroTier's libzt** — offers an in-process socket API, but uses a proprietary protocol (ZSSP) that is single-threaded and BSL-licensed, tied to ZeroTier's infrastructure.
- **Tailscale's tsnet** — Go-only, not available for .NET.

There is a gap: .NET developers who want in-process overlay networking with the widely-audited WireGuard protocol have no option.

## Vision

**WgSocket fills this gap.** A single NuGet package that lets any .NET 8+ application join a WireGuard network by swapping `System.Net.Sockets.Socket` for `WgSocket.Socket` — a one-line type change.

No daemon. No TUN adapter. No elevated privileges. Just a UDP socket, WireGuard crypto, and a userspace TCP/IP stack — all running inside your process.

## Goals

- Deliver a NuGet package (`WgSocket`) targeting .NET 8+ with in-process WireGuard connectivity and zero OS-level dependencies beyond a single UDP socket
- Mirror the `System.Net.Sockets.Socket` API surface: `Bind()`, `Listen()`, `Accept()`, `Connect()`, `Send()`, `Receive()` with familiar signatures
- Ship native binaries for win-x64, linux-x64, osx-x64, osx-arm64 inside the NuGet package
- Achieve throughput competitive with WireGuard kernel module on single-stream workloads
- Maintain a fully open-source licence stack (BSD-3 + MIT + project licence)
- Keep the novel code surface small (~200-400 lines Rust glue, ~300 lines C# wrapper) to minimise attack surface and maintenance burden

## Target Users

- **ASP.NET Core services** needing WireGuard without a system daemon (e.g. Claude Orchestrator managing sessions across machines)
- **Desktop/CLI applications** embedding overlay networking (custom browsers, game clients, P2P tools)
- **Hangfire/background workers** reaching WireGuard resources without elevated privileges
- **.NET developers** who want the security and simplicity of WireGuard without the operational overhead of system-level setup

## Non-Goals

- No built-in control plane, peer discovery, or NAT traversal coordination
- No Layer 2 (Ethernet bridging) — WireGuard is Layer 3 only
- No key generation or management — consumers use standard WireGuard tooling
- Not a replacement for full mesh networking solutions (Tailscale, NetBird) — WgSocket is the data plane building block

## Differentiators

- **Only in-process WireGuard socket API for .NET** — nothing equivalent exists on NuGet
- **Genuinely open source** — BSD-3 + MIT, no BSL restrictions
- **Multi-threaded** — WireGuard's design, not ZeroTier's single-threaded ZSSP
- **Interoperable** — works with any WireGuard peer (kernel, wireguard-go, boringtun)
- **Minimal novel code** — thin composition layer over battle-tested components