# WgSocket.net

A .NET library providing a `System.Net.Sockets.Socket`-compatible API for WireGuard overlay networking, running entirely in userspace with no daemon, no TUN adapter, and no elevated privileges.

## What is this?

WgSocket composes Cloudflare's [boringtun](https://github.com/cloudflare/boringtun) (WireGuard protocol, BSD-3) with [smoltcp](https://github.com/smoltcp-rs/smoltcp) (userspace TCP/IP stack, MIT) via a thin Rust glue crate, consumed from C# via P/Invoke. The result is a NuGet package that lets any .NET application join a WireGuard network with a one-line type change.

Nothing equivalent exists on NuGet today.

## Quick Start

```bash
dotnet add package WgSocket
```

### Before (system sockets)

```csharp
using System.Net.Sockets;

var socket = new Socket(AddressFamily.InterNetwork, SocketType.Stream, ProtocolType.Tcp);
socket.Connect(new IPEndPoint(IPAddress.Parse("10.0.0.2"), 8080));
socket.Send(data);
```

### After (WireGuard tunnel)

```csharp
using WgSocket;

var device = new WgDevice(new WgConfig
{
    PrivateKey = myPrivateKey,
    ListenPort = 51820,
    Address = "10.0.0.1/24",
    Peers = new[] { new WgPeer
    {
        PublicKey = peerPublicKey,
        Endpoint = "203.0.113.1:51820",
        AllowedIPs = "10.0.0.0/24"
    }}
});

using var socket = device.CreateSocket();
socket.Connect(new IPEndPoint(IPAddress.Parse("10.0.0.2"), 8080));
socket.Send(data);
```

Same API. No daemon. No TUN. No elevated privileges.

## Features

- **Drop-in replacement** — mirrors `System.Net.Sockets.Socket` API (`Connect`, `Bind`, `Listen`, `Accept`, `Send`, `Receive` + async variants)
- **Zero OS dependencies** — only needs a single UDP socket. No kernel modules, no TUN adapters, no external daemons
- **Cross-platform** — ships native binaries for `win-x64`, `linux-x64`, `osx-x64`, `osx-arm64`
- **Fully open source** — BSD-3 (boringtun) + MIT (smoltcp) + project licence
- **Interoperable** — works with any WireGuard peer (kernel, wireguard-go, other boringtun users)
- **Multi-threaded** — leverages WireGuard's concurrent design (unlike ZeroTier's single-threaded ZSSP)
- **AOT-compatible** — uses `LibraryImport` source-generated P/Invoke

## Architecture

```
Consumer App (.NET 8+)
    ↕  WgSocket C# Library (P/Invoke)
    ↕  wgsocket-native Rust cdylib
    ↕  boringtun (WireGuard crypto) + smoltcp (TCP/IP stack)
    ↕  Single real UDP socket
```

See [.project/ARCHITECTURE.md](.project/ARCHITECTURE.md) for the full component map and data flow.

## Repository Structure

```
├── src/
│   ├── wgsocket-native/         # Rust crate: boringtun + smoltcp glue + C ABI
│   ├── WgSocket/                # C# class library (.NET 8+)
│   └── WgSocket.Tests/          # xUnit test project
├── native/                      # Pre-built native binaries (CI output)
├── samples/
│   ├── EchoServer/              # TCP echo server example
│   └── ChatClient/              # P2P chat example
├── build/                       # CI/CD scripts
├── .project/                    # ProjectMan docs & work items
└── WgSocket.sln
```

## Building from Source

**Prerequisites:** .NET 8+ SDK, Rust toolchain (stable)

```bash
# Rust native library
cd src/wgsocket-native && cargo build --release

# C# library + tests
dotnet build
dotnet test
```

## Project Documentation

Detailed docs are in [.project/](.project/):

- [PROJECT.md](.project/PROJECT.md) — overview, team, conventions
- [ARCHITECTURE.md](.project/ARCHITECTURE.md) — component map, data flow, key patterns
- [DECISIONS.md](.project/DECISIONS.md) — architectural decision records (ADRs)
- [SECURITY.md](.project/SECURITY.md) — threat model, authentication, key handling
- [INFRASTRUCTURE.md](.project/INFRASTRUCTURE.md) — CI/CD, cross-compilation, NuGet packaging
- [VISION.md](.project/VISION.md) — problem statement, goals, differentiators

## Status

**Greenfield — Design phase.** Architecture defined, project fully scoped (11 epics, 67 stories, 653 tasks). No code written yet.

## License

TBD (MIT or Apache-2.0)
