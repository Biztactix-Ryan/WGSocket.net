# WgSocket.net

[![CI](https://github.com/YOUR_ORG/wgsocket-net/actions/workflows/ci.yml/badge.svg)](https://github.com/YOUR_ORG/wgsocket-net/actions/workflows/ci.yml)
[![NuGet](https://img.shields.io/nuget/v/WgSocket.svg)](https://www.nuget.org/packages/WgSocket)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

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

## Code Examples

### Echo Server

```csharp
using var device = new WgDevice(config);
using var listener = device.CreateSocket();

listener.Bind(new IPEndPoint(IPAddress.Parse("10.0.0.1"), 9000));
listener.Listen(10);

while (true)
{
    using var client = await listener.AcceptAsync();
    var buffer = new byte[1024];
    int received = await client.ReceiveAsync(buffer);
    await client.SendAsync(buffer.AsMemory(0, received));
}
```

### Client Connection

```csharp
using var device = new WgDevice(config);
using var socket = device.CreateSocket();

await socket.ConnectAsync(new IPEndPoint(IPAddress.Parse("10.0.0.2"), 9000));
await socket.SendAsync("Hello"u8.ToArray());

var response = new byte[1024];
int bytes = await socket.ReceiveAsync(response);
Console.WriteLine(Encoding.UTF8.GetString(response, 0, bytes));
```

### NetworkStream with Async I/O

```csharp
using var device = new WgDevice(config);
using var socket = device.CreateSocket();
await socket.ConnectAsync(new IPEndPoint(IPAddress.Parse("10.0.0.2"), 8080));

await using var stream = new NetworkStream(socket, ownsSocket: true);
using var reader = new StreamReader(stream);
using var writer = new StreamWriter(stream) { AutoFlush = true };

await writer.WriteLineAsync("GET / HTTP/1.0\r\n");
string? line = await reader.ReadLineAsync();
```

## API Overview

| Type | Description |
|------|-------------|
| `WgDevice` | Manages a WireGuard tunnel lifecycle; creates sockets via `CreateSocket()` |
| `WgConfig` | Tunnel configuration: private key, listen port, address, and peers |
| `WgPeer` | Peer configuration: public key, endpoint, allowed IPs, optional PSK |
| `Socket` | Drop-in replacement for `System.Net.Sockets.Socket` over the tunnel |
| `NetworkStream` | Stream adapter for use with `StreamReader`, `StreamWriter`, ASP.NET Core |

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

**Prerequisites:** .NET 9+ SDK, Rust toolchain (stable)

```bash
# Rust native library
cd src/wgsocket-native && cargo build --release

# C# library + tests
dotnet build
dotnet test
```

For cross-compilation setup (all 4 target platforms), toolchain prerequisites, and output directory layout, see [docs/BUILDING.md](docs/BUILDING.md).

## Project Documentation

Detailed docs are in [.project/](.project/):

- [PROJECT.md](.project/PROJECT.md) — overview, team, conventions
- [ARCHITECTURE.md](.project/ARCHITECTURE.md) — component map, data flow, key patterns
- [DECISIONS.md](.project/DECISIONS.md) — architectural decision records (ADRs)
- [SECURITY.md](.project/SECURITY.md) — threat model, authentication, key handling
- [INFRASTRUCTURE.md](.project/INFRASTRUCTURE.md) — CI/CD, cross-compilation, NuGet packaging
- [VISION.md](.project/VISION.md) — problem statement, goals, differentiators

## Links

- [**Samples**](samples/) — Echo server, chat client, and more example applications
- [**Architecture**](.project/ARCHITECTURE.md) — Component map, data flow, and design patterns
- [**Contributing**](CONTRIBUTING.md) — How to contribute, code style, and PR guidelines

## Status

**Greenfield — Design phase.** Architecture defined, project fully scoped (11 epics, 67 stories, 653 tasks). No code written yet.

## License

MIT — see [LICENSE](LICENSE) for details.
