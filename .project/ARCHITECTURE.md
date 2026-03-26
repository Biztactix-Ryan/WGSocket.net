# WgSocket.net — Architecture

## System Overview

WgSocket is a **layered composition library** — it assembles two existing, battle-tested components (boringtun for WireGuard crypto, smoltcp for userspace TCP/IP) into a single in-process network stack, then exposes that stack to .NET via a C FFI boundary and P/Invoke wrapper.

The architecture follows the "userspace network stack" pattern used by Cloudflare WARP (mobile), Tailscale (iOS/Android via gVisor netstack), and ZeroTier's libzt (via lwIP). The entire TCP/IP stack and VPN crypto layer runs inside your process, needing only a single real UDP socket to the outside world.

This is **Model A** (in-process socket replacement), not **Model B** (daemon/adapter management). The application's sockets ARE the overlay network — no system-level network changes, no elevated privileges, no external daemon.

## Component Map

```
┌─────────────────────────────────────────────────────┐
│  Consumer Application (.NET 8+)                     │
│  var socket = new WgSocket.Socket(...)              │
│  socket.Connect(peerEndpoint)                       │
│  socket.Send(data) / socket.Receive(buffer)         │
├─────────────────────────────────────────────────────┤
│  WgSocket C# Library (WgSocket.dll)        ← NuGet │
│  Socket.cs      — System.Net.Sockets-compatible API │
│  WgDevice.cs    — Tunnel lifecycle (init/teardown)  │
│  NativeMethods.cs — LibraryImport P/Invoke decls    │
├────────────────── P/Invoke (C ABI) ─────────────────┤
│  wgsocket-native (libwgsocket.dll/.so/.dylib) ← Rust│
│  lib.rs — C FFI exports                            │
│  ├── wg_device_new(config) → handle                 │
│  ├── wg_connect(handle, addr, port) → fd            │
│  ├── wg_listen(handle, addr, port) → fd             │
│  ├── wg_accept(handle, listener_fd) → fd            │
│  ├── wg_send(handle, fd, buf, len) → bytes_sent     │
│  ├── wg_recv(handle, fd, buf, len) → bytes_recv     │
│  ├── wg_close(handle, fd)                           │
│  └── wg_device_free(handle)                         │
│  tunnel.rs — Composition engine (boringtun ↔ smoltcp)│
├─────────────────────────────────────────────────────┤
│  boringtun (statically linked)                      │
│  Noise_IKpsk2 handshake, ChaCha20-Poly1305,         │
│  key exchange, anti-replay, cookie DoS mitigation   │
├─────────────────────────────────────────────────────┤
│  smoltcp (statically linked)                        │
│  TCP state machine, UDP mux, IP routing,            │
│  socket buffer management                           │
├─────────────────────────────────────────────────────┤
│  OS Kernel — one real UDP socket (e.g. 0.0.0.0:51820)│
└─────────────────────────────────────────────────────┘
```

## Tech Stack

| Layer | Technology | Rationale |
|---|---|---|
| Application API | C# / .NET 8+ | Target ecosystem. System.Net.Sockets is the natural interface. |
| Interop | `LibraryImport` (source-generated P/Invoke) | AOT-compatible, faster than legacy `DllImport`. |
| Native glue | Rust | Memory safety without GC. Excellent cross-compilation via `cargo build --target`. |
| WireGuard protocol | boringtun (BSD-3) | Cloudflare-maintained, production-proven, clean encrypt/decrypt API. |
| TCP/IP stack | smoltcp (MIT) | Purpose-built for userspace/embedded. ~Gbps throughput in loopback. |
| Header generation | cbindgen | Single source of truth for C ABI, prevents P/Invoke drift. |
| Testing | cargo test + xUnit | Rust unit tests + C# integration tests for full roundtrip. |
| CI/CD | GitHub Actions | Matrix build across 4 platform targets, NuGet packaging. |

## Data Flow

### Outbound (application sends data through the tunnel)

```
1. Consumer calls socket.Send(data)
2. P/Invoke → wg_send(handle, fd, buf, len)
3. Rust glue writes data into smoltcp's socket buffer
4. smoltcp segments data, adds TCP/IP headers, produces IP packets
5. Rust glue passes outbound IP packets to boringtun's encrypt
6. boringtun wraps in WireGuard transport messages (ChaCha20-Poly1305)
7. Rust glue sends encrypted packets via real UDP socket
```

### Inbound (data arrives from the tunnel)

```
1. Real UDP socket receives encrypted WireGuard packet
2. boringtun validates, decrypts → plaintext IP packet
3. smoltcp processes TCP/IP headers, deposits payload in socket buffer
4. wg_recv copies data from socket buffer
5. P/Invoke returns → Socket.Receive() returns data to consumer
```

### Handshake (on first contact or rekey)

```
1. Consumer calls socket.Connect() or sends first packet
2. boringtun initiates Noise_IKpsk2 handshake via real UDP socket
3. Handshake completes → derives session keys
4. Rekey every 2 minutes / 2^64 bytes (WireGuard protocol spec)
```

## Key Patterns

### Handle-Based FFI

Opaque handles (`*mut Device` cast to `usize`) rather than exposing Rust types. C# holds `nint` handles. Rust validates handles on entry and returns error codes for invalid handles. Prevents use-after-free at the cost of a hash-map lookup per call.

### Poll-Driven smoltcp Integration

smoltcp is "sans-I/O" — the Rust glue runs a poll loop on a dedicated thread per `WgDevice`:

```
loop {
    poll real UDP socket for incoming packets (non-blocking)
    feed received packets through boringtun → smoltcp
    poll smoltcp for outbound packets
    feed outbound packets through boringtun → real UDP socket
    sleep until next smoltcp timer or socket readability
}
```

### NuGet Runtime ID (RID) Packaging

```
runtimes/win-x64/native/libwgsocket.dll
runtimes/linux-x64/native/libwgsocket.so
runtimes/osx-x64/native/libwgsocket.dylib
runtimes/osx-arm64/native/libwgsocket.dylib
```

The .NET runtime automatically loads the correct native library for the current platform.

### Disposable Resource Lifecycle

```csharp
using var device = new WgDevice(config);    // wg_device_new
using var socket = device.CreateSocket();    // allocates virtual socket in smoltcp
socket.Connect(endpoint);                   // wg_connect
socket.Send(data);                          // wg_send
// Dispose order: socket first (wg_close), then device (wg_device_free)
// Ref-counting in Rust prevents device teardown while sockets are live
```

## Integration Points

### Peer WireGuard Endpoints

Communicates with any standard WireGuard peer (kernel, wireguard-go, boringtun, another WgSocket instance). Configured via: public key, endpoint (IP:port), allowed IPs, optional PSK.

### Consumer Applications

- ASP.NET Core services needing WireGuard without a system daemon
- Desktop/CLI apps embedding overlay networking
- Hangfire/background workers reaching WireGuard resources without elevated privileges

### No External Services

No control plane, telemetry, or external service communication. Purely local-to-peer networking. Control plane functionality is the consumer's responsibility.