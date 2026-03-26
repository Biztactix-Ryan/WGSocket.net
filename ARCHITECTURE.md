# Architecture — WgSocket

## System Overview

WgSocket is a **layered composition library** — it assembles two existing, battle-tested components (boringtun for WireGuard crypto, smoltcp for userspace TCP/IP) into a single in-process network stack, then exposes that stack to .NET via a C FFI boundary and P/Invoke wrapper.

The architecture follows the "userspace network stack" pattern used by Cloudflare WARP (mobile), Tailscale (iOS/Android via gVisor netstack), and ZeroTier's libzt (via lwIP). The key insight is that the entire TCP/IP stack and VPN crypto layer can run inside your process, needing only a single real UDP socket to the outside world.

This is **Model A** (in-process socket replacement), not **Model B** (daemon/adapter management). The application's sockets ARE the overlay network — no system-level network changes, no elevated privileges, no external daemon.

## Component Map

```
┌─────────────────────────────────────────────────────┐
│  Consumer Application (.NET 8+)                     │
│                                                     │
│  var socket = new WgSocket.Socket(...)              │
│  socket.Connect(peerEndpoint)                       │
│  socket.Send(data)                                  │
│  var received = socket.Receive(buffer)              │
├─────────────────────────────────────────────────────┤
│  WgSocket C# Library (WgSocket.dll)                 │  ← NuGet package
│                                                     │
│  Socket.cs      — System.Net.Sockets-compatible API │
│  WgDevice.cs    — Tunnel lifecycle (init/teardown)  │
│  NativeMethods.cs — LibraryImport P/Invoke decls    │
├────────────────── P/Invoke (C ABI) ─────────────────┤
│  wgsocket-native (libwgsocket.dll/.so/.dylib)       │  ← Rust cdylib
│                                                     │
│  lib.rs         — C FFI exports                     │
│  ├── wg_device_new(config) → handle                 │
│  ├── wg_connect(handle, addr, port) → fd            │
│  ├── wg_listen(handle, addr, port) → fd             │
│  ├── wg_accept(handle, listener_fd) → fd            │
│  ├── wg_send(handle, fd, buf, len) → bytes_sent     │
│  ├── wg_recv(handle, fd, buf, len) → bytes_recv     │
│  ├── wg_close(handle, fd)                           │
│  └── wg_device_free(handle)                         │
│                                                     │
│  tunnel.rs      — Composition engine                │
│  ├── Wires boringtun encrypted output → smoltcp     │
│  ├── Wires smoltcp IP frames → boringtun encrypt    │
│  └── Manages the single real UDP socket             │
├─────────────────────────────────────────────────────┤
│  boringtun (Rust crate, statically linked)          │
│                                                     │
│  WireGuard protocol implementation:                 │
│  ├── Noise_IKpsk2 handshake                         │
│  ├── ChaCha20-Poly1305 packet encrypt/decrypt       │
│  ├── Key exchange and session management             │
│  └── Anti-replay, cookie DoS mitigation             │
├─────────────────────────────────────────────────────┤
│  smoltcp (Rust crate, statically linked)            │
│                                                     │
│  Userspace TCP/IP stack:                            │
│  ├── TCP state machine (SYN, ACK, FIN, etc.)        │
│  ├── UDP multiplexing                               │
│  ├── IP routing table                               │
│  ├── ARP / NDP (if needed for L2 emulation)         │
│  └── Socket buffer management                       │
├─────────────────────────────────────────────────────┤
│  OS Kernel                                          │
│                                                     │
│  One real UDP socket (e.g. 0.0.0.0:51820)           │
│  ← the ONLY system resource consumed                │
└─────────────────────────────────────────────────────┘
```

## Tech Stack

| Layer | Technology | Rationale |
|---|---|---|
| **Application API** | C# / .NET 8+ | Target ecosystem. System.Net.Sockets API is the natural interface for .NET developers. |
| **Interop** | `LibraryImport` (source-generated P/Invoke) | AOT-compatible, faster than legacy `DllImport`, catches marshalling errors at compile time. |
| **Native glue** | Rust | Memory safety without GC. The glue crate touches raw pointers at the FFI boundary — Rust's ownership model makes this as safe as possible. Excellent cross-compilation story via `cargo build --target`. |
| **WireGuard protocol** | boringtun (Rust, BSD-3) | Cloudflare-maintained, production-proven on millions of devices, clean API for encrypt/decrypt without OS dependencies. |
| **TCP/IP stack** | smoltcp (Rust, MIT) | Purpose-built for userspace/embedded use. No heap allocation required. ~Gbps throughput against Linux TCP in loopback tests. |
| **Header generation** | cbindgen | Generates `wgsocket.h` from Rust source — single source of truth for the C ABI, prevents P/Invoke drift. |
| **Testing** | cargo test + xUnit | Rust unit tests for packet composition; C# integration tests for full roundtrip through the stack. |
| **CI/CD** | GitHub Actions | Matrix build across 4 platform targets, NuGet packaging. |

## Data Flow

### Outbound (application sends data through the tunnel)

```
1. Consumer calls socket.Send(data)
2. WgSocket.Socket.Send() → P/Invoke → wg_send(handle, fd, buf, len)
3. Rust glue writes data into smoltcp's socket buffer
4. smoltcp runs its TCP state machine:
   - Segments the data
   - Adds TCP/IP headers
   - Produces IP packets
5. Rust glue takes smoltcp's outbound IP packets
6. Passes them to boringtun's encrypt function
7. boringtun wraps them in WireGuard transport data messages
   (ChaCha20-Poly1305 encrypted, with counter for anti-replay)
8. Rust glue sends the encrypted WireGuard packets via the
   single real UDP socket to the peer's endpoint
```

### Inbound (data arrives from the tunnel)

```
1. Real UDP socket receives encrypted WireGuard packet
2. Rust glue passes it to boringtun's decrypt function
3. boringtun validates, decrypts → produces plaintext IP packet
4. Rust glue feeds the IP packet into smoltcp
5. smoltcp processes TCP/IP headers:
   - ACKs, flow control, reassembly
   - Deposits payload into the appropriate socket buffer
6. wg_recv(handle, fd, buf, len) copies data from socket buffer
7. P/Invoke returns → WgSocket.Socket.Receive() returns data to consumer
```

### Handshake (on first contact or rekey)

```
1. Consumer calls socket.Connect() or sends first packet
2. If no session exists for the target peer, boringtun initiates
   a Noise_IKpsk2 handshake:
   - Sends Initiation message via real UDP socket
   - Receives Response message
   - Derives session keys
3. Once handshake completes, data packets flow as above
4. Rekey occurs automatically every 2 minutes / 2^64 bytes
   (WireGuard protocol spec)
```

## Key Patterns

### Handle-Based FFI

The C ABI uses opaque handles (`*mut Device` cast to `usize`) rather than exposing Rust types across the boundary. The C# side holds `nint` (native int) handles and passes them back on every call. The Rust side validates handles on entry and returns error codes for invalid handles. This prevents use-after-free at the cost of a hash-map lookup per call.

### Poll-Driven smoltcp Integration

smoltcp is designed as a "sans-I/O" stack — it doesn't do I/O itself, it tells you when to do I/O. The Rust glue runs a poll loop:

```
loop {
    poll real UDP socket for incoming packets (non-blocking)
    feed any received packets through boringtun → smoltcp
    poll smoltcp for outbound packets
    feed any outbound packets through boringtun → real UDP socket
    sleep until next smoltcp timer or socket readability
}
```

This loop runs on a dedicated thread per `WgDevice`. Application threads interact via smoltcp's socket buffers (which are thread-safe behind smoltcp's `Interface` lock).

### NuGet Runtime ID (RID) Packaging

Native binaries are placed in the NuGet package under:
```
runtimes/win-x64/native/libwgsocket.dll
runtimes/linux-x64/native/libwgsocket.so
runtimes/osx-x64/native/libwgsocket.dylib
runtimes/osx-arm64/native/libwgsocket.dylib
```

The .NET runtime automatically loads the correct native library for the current platform. The `.csproj` uses `<NativeLibrary>` items to wire this up.

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

The library communicates with standard WireGuard peers — any implementation (kernel WireGuard, wireguard-go, boringtun, another WgSocket instance). Peers are configured via standard WireGuard parameters: public key, endpoint (IP:port), allowed IPs, and optional PSK.

### Consumer Applications (Primary Integration)

The library is consumed as a NuGet package. Target consumers include:

- **ASP.NET Core services** that need to communicate over WireGuard without requiring a system-level WireGuard daemon (e.g. the Claude Orchestrator managing sessions across physical machines)
- **Desktop/CLI applications** that embed overlay networking (e.g. a custom Firefox build, game clients, peer-to-peer tools)
- **Hangfire/background job workers** that need to reach resources on a WireGuard network without elevated privileges

### No External Services

The library does not communicate with any external service, control plane, or telemetry endpoint. It is purely a local-to-peer networking library. This is a deliberate design choice — control plane functionality (peer discovery, key distribution, ACL management) is the consumer's responsibility.
