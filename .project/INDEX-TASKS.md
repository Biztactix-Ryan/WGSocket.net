# Tasks

| ID | Title | Status | Points | Tags | Assignee | Depends On | Story |
| -- | ----- | ------ | ------ | ---- | -------- | ---------- | ----- |
| [US-WNE-1-1](tasks/US-WNE-1-1.md) | Test: Cargo.toml defines cdylib crate type with boringtun and smoltcp dependencies | ✅ done | 1 |  | claude | US-WNE-1-5, US-WNE-1-6 | [US-WNE-1](stories/US-WNE-1.md) |
| [US-WNE-1-2](tasks/US-WNE-1-2.md) | Test: cargo build produces platform-appropriate shared library (.so/.dll/.dylib) | ✅ done | 1 |  | claude | US-WNE-1-5, US-WNE-1-6 | [US-WNE-1](stories/US-WNE-1.md) |
| [US-WNE-1-3](tasks/US-WNE-1-3.md) | Test: cargo test runs empty test suite successfully | ✅ done | 1 |  | claude | US-WNE-1-5 | [US-WNE-1](stories/US-WNE-1.md) |
| [US-WNE-1-4](tasks/US-WNE-1-4.md) | Test: Crate compiles on Linux and macOS and Windows targets | ✅ done | 1 |  | claude | US-WNE-1-7 | [US-WNE-1](stories/US-WNE-1.md) |
| [US-WNE-1-5](tasks/US-WNE-1-5.md) | Initialize Cargo project with cdylib crate type | ✅ done | 1 |  | claude | — | [US-WNE-1](stories/US-WNE-1.md) |
| [US-WNE-1-6](tasks/US-WNE-1-6.md) | Add boringtun and smoltcp dependencies with feature flags | ✅ done | 1 |  | claude | US-WNE-1-5 | [US-WNE-1](stories/US-WNE-1.md) |
| [US-WNE-1-7](tasks/US-WNE-1-7.md) | Add cross-platform build configuration and CI essentials | ✅ done | 1 |  | claude | US-WNE-1-5 | [US-WNE-1](stories/US-WNE-1.md) |
| [US-WNE-1-8](tasks/US-WNE-1-8.md) | Verify cdylib builds and test suite runs on all targets | ✅ done | 1 |  | claude | US-WNE-1-5, US-WNE-1-6, US-WNE-1-7 | [US-WNE-1](stories/US-WNE-1.md) |
| [US-WNE-10-1](tasks/US-WNE-10-1.md) | Test: WgDeviceHandle lifecycle and IsInvalid | ✅ done | 1 |  | claude | US-WNE-10-6 | [US-WNE-10](stories/US-WNE-10.md) |
| [US-WNE-10-2](tasks/US-WNE-10-2.md) | Test: WgSocketHandle lifecycle and platform-conditional IsInvalid | ✅ done | 1 |  | claude | US-WNE-10-7 | [US-WNE-10](stories/US-WNE-10.md) |
| [US-WNE-10-3](tasks/US-WNE-10-3.md) | Test: ReleaseHandle calls correct native free function | ✅ done | 1 |  | claude | US-WNE-10-6, US-WNE-10-7 | [US-WNE-10](stories/US-WNE-10.md) |
| [US-WNE-10-4](tasks/US-WNE-10-4.md) | Test: ObjectDisposedException on use-after-dispose | ✅ done | 1 |  | claude | US-WNE-10-6, US-WNE-10-7, US-WNE-10-8 | [US-WNE-10](stories/US-WNE-10.md) |
| [US-WNE-10-5](tasks/US-WNE-10-5.md) | Test: CriticalFinalizerObject cleanup guarantee | ✅ done | 1 |  | claude | US-WNE-10-6, US-WNE-10-7 | [US-WNE-10](stories/US-WNE-10.md) |
| [US-WNE-10-6](tasks/US-WNE-10-6.md) | Implement WgDeviceHandle SafeHandle subclass | ✅ done | 2 |  | claude | — | [US-WNE-10](stories/US-WNE-10.md) |
| [US-WNE-10-7](tasks/US-WNE-10-7.md) | Implement WgSocketHandle SafeHandle subclass | ✅ done | 2 |  | claude | — | [US-WNE-10](stories/US-WNE-10.md) |
| [US-WNE-10-8](tasks/US-WNE-10-8.md) | Wire SafeHandles into NativeMethods P/Invoke signatures | ✅ done | 1 |  | claude | US-WNE-10-6, US-WNE-10-7 | [US-WNE-10](stories/US-WNE-10.md) |
| [US-WNE-11-1](tasks/US-WNE-11-1.md) | Test: WgException hierarchy structure and ErrorCode property | ✅ done | 1 |  | claude | US-WNE-11-5 | [US-WNE-11](stories/US-WNE-11.md) |
| [US-WNE-11-2](tasks/US-WNE-11-2.md) | Test: Correct exception subclass thrown for each error code | ✅ done | 1 |  | claude | US-WNE-11-5, US-WNE-11-6 | [US-WNE-11](stories/US-WNE-11.md) |
| [US-WNE-11-3](tasks/US-WNE-11-3.md) | Test: Native error string from wg_last_error included in exception message | ✅ done | 1 |  | claude | US-WNE-11-6 | [US-WNE-11](stories/US-WNE-11.md) |
| [US-WNE-11-4](tasks/US-WNE-11-4.md) | Test: ThrowIfError returns cleanly on success codes | ✅ done | 1 |  | claude | US-WNE-11-6 | [US-WNE-11](stories/US-WNE-11.md) |
| [US-WNE-11-5](tasks/US-WNE-11-5.md) | Define WgException hierarchy | ✅ done | 2 |  | claude | — | [US-WNE-11](stories/US-WNE-11.md) |
| [US-WNE-11-6](tasks/US-WNE-11-6.md) | Implement ThrowIfError helper and wg_last_error integration | ✅ done | 1 |  | claude | US-WNE-11-5 | [US-WNE-11](stories/US-WNE-11.md) |
| [US-WNE-12-1](tasks/US-WNE-12-1.md) | Test: Send operations accept ReadOnlySpan and pin correctly | ✅ done | 1 |  | claude | US-WNE-12-6 | [US-WNE-12](stories/US-WNE-12.md) |
| [US-WNE-12-2](tasks/US-WNE-12-2.md) | Test: Receive operations write to Span and report actual length | ✅ done | 1 |  | claude | US-WNE-12-7 | [US-WNE-12](stories/US-WNE-12.md) |
| [US-WNE-12-3](tasks/US-WNE-12-3.md) | Test: Buffer pinning prevents GC relocation during P/Invoke | ✅ done | 1 |  | claude | US-WNE-12-6, US-WNE-12-7 | [US-WNE-12](stories/US-WNE-12.md) |
| [US-WNE-12-4](tasks/US-WNE-12-4.md) | Test: UTF-8 config string marshalling with null termination | ✅ done | 1 |  | claude | US-WNE-12-8 | [US-WNE-12](stories/US-WNE-12.md) |
| [US-WNE-12-5](tasks/US-WNE-12-5.md) | Test: Key material validated as 32-byte ReadOnlySpan and never string-allocated | ✅ done | 1 |  | claude | US-WNE-12-8 | [US-WNE-12](stories/US-WNE-12.md) |
| [US-WNE-12-6](tasks/US-WNE-12-6.md) | Implement Span-based send buffer marshalling | ✅ done | 2 |  | claude | — | [US-WNE-12](stories/US-WNE-12.md) |
| [US-WNE-12-7](tasks/US-WNE-12-7.md) | Implement Span-based receive buffer marshalling | ✅ done | 2 |  | claude | — | [US-WNE-12](stories/US-WNE-12.md) |
| [US-WNE-12-8](tasks/US-WNE-12-8.md) | Implement UTF-8 config string and key material marshalling | ✅ done | 2 |  | claude | — | [US-WNE-12](stories/US-WNE-12.md) |
| [US-WNE-13-1](tasks/US-WNE-13-1.md) | Test: Library resolves from runtimes/{rid}/native/ path | ✅ done | 1 |  | claude | US-WNE-13-5 | [US-WNE-13](stories/US-WNE-13.md) |
| [US-WNE-13-2](tasks/US-WNE-13-2.md) | Test: DllNotFoundException contains helpful diagnostic message | ✅ done | 1 |  | claude | US-WNE-13-6 | [US-WNE-13](stories/US-WNE-13.md) |
| [US-WNE-13-3](tasks/US-WNE-13-3.md) | Test: Platform RID resolution covers all supported targets | ✅ done | 1 |  | claude | US-WNE-13-5 | [US-WNE-13](stories/US-WNE-13.md) |
| [US-WNE-13-4](tasks/US-WNE-13-4.md) | Test: Custom resolver falls back to default when custom probing fails | ✅ done | 1 |  | claude | US-WNE-13-5 | [US-WNE-13](stories/US-WNE-13.md) |
| [US-WNE-13-5](tasks/US-WNE-13-5.md) | Implement NativeLibrary.SetDllImportResolver for wgsocket | ✅ done | 2 |  | claude | — | [US-WNE-13](stories/US-WNE-13.md) |
| [US-WNE-13-6](tasks/US-WNE-13-6.md) | Implement enhanced DllNotFoundException diagnostics | ✅ done | 1 |  | claude | — | [US-WNE-13](stories/US-WNE-13.md) |
| [US-WNE-14-1](tasks/US-WNE-14-1.md) | Test: wg_device_new accepts a null-terminated config string (wg.conf format) and returns a positive handle on success... | ✅ done | — |  | — | — | [US-WNE-14](stories/US-WNE-14.md) |
| [US-WNE-14-2](tasks/US-WNE-14-2.md) | Test: wg_device_new accepts a WgConfig struct pointer as an alternative to string config | ✅ done | — |  | — | — | [US-WNE-14](stories/US-WNE-14.md) |
| [US-WNE-14-3](tasks/US-WNE-14-3.md) | Test: wg_device_free releases all resources associated with the handle | ✅ done | — |  | — | — | [US-WNE-14](stories/US-WNE-14.md) |
| [US-WNE-14-4](tasks/US-WNE-14-4.md) | Test: Double-free is safe -- returns WG_ERR_INVALID_HANDLE without crashing or UB | ✅ done | — |  | — | — | [US-WNE-14](stories/US-WNE-14.md) |
| [US-WNE-14-5](tasks/US-WNE-14-5.md) | Test: Config parsing errors are reported via return code and retrievable via wg_last_error | ✅ done | — |  | — | — | [US-WNE-14](stories/US-WNE-14.md) |
| [US-WNE-14-6](tasks/US-WNE-14-6.md) | Implement handle table and wg_device_new with string config | ✅ done | 2 |  | — | — | [US-WNE-14](stories/US-WNE-14.md) |
| [US-WNE-14-7](tasks/US-WNE-14-7.md) | Implement wg_device_new_from_struct with WgConfig FFI struct | ✅ done | 1 |  | — | US-WNE-14-6 | [US-WNE-14](stories/US-WNE-14.md) |
| [US-WNE-14-8](tasks/US-WNE-14-8.md) | Implement wg_device_free with double-free safety | ✅ done | 1 |  | — | US-WNE-14-6 | [US-WNE-14](stories/US-WNE-14.md) |
| [US-WNE-14-9](tasks/US-WNE-14-9.md) | Test device lifecycle: create, free, double-free, invalid config | ✅ done | 2 |  | — | US-WNE-14-6, US-WNE-14-7, US-WNE-14-8 | [US-WNE-14](stories/US-WNE-14.md) |
| [US-WNE-15-1](tasks/US-WNE-15-1.md) | Test: Outbound path works: smoltcp IP packet -> boringtun encrypt -> UDP send | ✅ done | 2 |  | claude | US-WNE-15-6 | [US-WNE-15](stories/US-WNE-15.md) |
| [US-WNE-15-2](tasks/US-WNE-15-2.md) | Test: Inbound path works: UDP recv -> boringtun decrypt -> smoltcp process | ✅ done | 2 |  | claude | US-WNE-15-7 | [US-WNE-15](stories/US-WNE-15.md) |
| [US-WNE-15-3](tasks/US-WNE-15-3.md) | Test: Handshake packets are handled correctly and not fed to smoltcp | ✅ done | 2 |  | claude | US-WNE-15-8 | [US-WNE-15](stories/US-WNE-15.md) |
| [US-WNE-15-4](tasks/US-WNE-15-4.md) | Test: Timer-driven events (keepalive and rekey) fire correctly | ✅ done | 2 |  | claude | US-WNE-15-8 | [US-WNE-15](stories/US-WNE-15.md) |
| [US-WNE-15-5](tasks/US-WNE-15-5.md) | Test: The composition handles both TCP and UDP socket types | ✅ done | 2 |  | claude | US-WNE-15-6, US-WNE-15-7 | [US-WNE-15](stories/US-WNE-15.md) |
| [US-WNE-15-6](tasks/US-WNE-15-6.md) | Implement outbound packet path (smoltcp -> boringtun -> UDP) | ✅ done | 2 |  | claude | — | [US-WNE-15](stories/US-WNE-15.md) |
| [US-WNE-15-7](tasks/US-WNE-15-7.md) | Implement inbound packet path (UDP -> boringtun -> smoltcp) | ✅ done | 3 |  | claude | — | [US-WNE-15](stories/US-WNE-15.md) |
| [US-WNE-15-8](tasks/US-WNE-15-8.md) | Implement handshake packet routing and timer integration | ✅ done | 3 |  | claude | US-WNE-15-6, US-WNE-15-7 | [US-WNE-15](stories/US-WNE-15.md) |
| [US-WNE-15-9](tasks/US-WNE-15-9.md) | Test full outbound and inbound packet flow through composition engine | ✅ done | 3 |  | claude | US-WNE-15-6, US-WNE-15-7, US-WNE-15-8 | [US-WNE-15](stories/US-WNE-15.md) |
| [US-WNE-16-1](tasks/US-WNE-16-1.md) | Test: wg_connect initiates a TCP connection to a peer tunnel address and port and returns a socket fd or negative err... | ✅ done | — |  | — | US-WNE-16-6 | [US-WNE-16](stories/US-WNE-16.md) |
| [US-WNE-16-10](tasks/US-WNE-16-10.md) | Test connection lifecycle: connect, listen, accept, close, invalid handles | ✅ done | 2 |  | claude | US-WNE-16-6, US-WNE-16-7, US-WNE-16-8, US-WNE-16-9 | [US-WNE-16](stories/US-WNE-16.md) |
| [US-WNE-16-2](tasks/US-WNE-16-2.md) | Test: wg_listen binds and listens on a tunnel address and port and returns a listener fd or negative error code | ✅ done | — |  | — | US-WNE-16-7 | [US-WNE-16](stories/US-WNE-16.md) |
| [US-WNE-16-3](tasks/US-WNE-16-3.md) | Test: wg_accept blocks or polls for an incoming connection on a listener fd and returns a new socket fd or negative e... | ✅ done | — |  | — | US-WNE-16-8 | [US-WNE-16](stories/US-WNE-16.md) |
| [US-WNE-16-4](tasks/US-WNE-16-4.md) | Test: wg_close closes a socket or listener fd and returns WG_OK or negative error code | ✅ done | — |  | — | US-WNE-16-9 | [US-WNE-16](stories/US-WNE-16.md) |
| [US-WNE-16-5](tasks/US-WNE-16-5.md) | Test: All four functions validate the device handle and fd parameters returning WG_ERR_INVALID_HANDLE for bad handles | ✅ done | — |  | — | US-WNE-16-6 | [US-WNE-16](stories/US-WNE-16.md) |
| [US-WNE-16-6](tasks/US-WNE-16-6.md) | Implement wg_connect for outbound TCP connections | ✅ done | 2 |  | claude | — | [US-WNE-16](stories/US-WNE-16.md) |
| [US-WNE-16-7](tasks/US-WNE-16-7.md) | Implement wg_listen for binding a TCP listener | ✅ done | 2 |  | claude | US-WNE-16-6 | [US-WNE-16](stories/US-WNE-16.md) |
| [US-WNE-16-8](tasks/US-WNE-16-8.md) | Implement wg_accept for incoming connections | ✅ done | 2 |  | claude | US-WNE-16-7 | [US-WNE-16](stories/US-WNE-16.md) |
| [US-WNE-16-9](tasks/US-WNE-16-9.md) | Implement wg_close for socket and listener teardown | ✅ done | 1 |  | claude | US-WNE-16-6 | [US-WNE-16](stories/US-WNE-16.md) |
| [US-WNE-17-1](tasks/US-WNE-17-1.md) | Test: WgConfig class with PrivateKey (byte[]) and ListenPort and Address and Peers collection | ✅ done | 1 |  | claude | US-WNE-17-7 | [US-WNE-17](stories/US-WNE-17.md) |
| [US-WNE-17-2](tasks/US-WNE-17-2.md) | Test: WgPeer class with PublicKey and Endpoint and AllowedIPs and PresharedKey and PersistentKeepalive | ✅ done | 1 |  | claude | US-WNE-17-6 | [US-WNE-17](stories/US-WNE-17.md) |
| [US-WNE-17-3](tasks/US-WNE-17-3.md) | Test: Validation on construction rejects invalid keys/ports/addresses | ✅ done | 2 |  | claude | US-WNE-17-6, US-WNE-17-7 | [US-WNE-17](stories/US-WNE-17.md) |
| [US-WNE-17-4](tasks/US-WNE-17-4.md) | Test: ToString() redacts key material to prevent accidental logging | ✅ done | 1 |  | claude | US-WNE-17-7 | [US-WNE-17](stories/US-WNE-17.md) |
| [US-WNE-17-5](tasks/US-WNE-17-5.md) | Test: Builder or object initializer pattern for ergonomic construction | ✅ done | 1 |  | claude | US-WNE-17-7 | [US-WNE-17](stories/US-WNE-17.md) |
| [US-WNE-17-6](tasks/US-WNE-17-6.md) | Implement WgPeer configuration model | ✅ done | 1 |  | claude | — | [US-WNE-17](stories/US-WNE-17.md) |
| [US-WNE-17-7](tasks/US-WNE-17-7.md) | Implement WgConfig configuration model | ✅ done | 1 |  | claude | — | [US-WNE-17](stories/US-WNE-17.md) |
| [US-WNE-17-8](tasks/US-WNE-17-8.md) | Test WgPeer and WgConfig models | ✅ done | 1 |  | claude | US-WNE-17-6, US-WNE-17-7 | [US-WNE-17](stories/US-WNE-17.md) |
| [US-WNE-18-1](tasks/US-WNE-18-1.md) | Test: wg_send copies data from caller buffer into smoltcp socket send buffer and returns bytes actually sent | ✅ done | — |  | — | US-WNE-18-6 | [US-WNE-18](stories/US-WNE-18.md) |
| [US-WNE-18-2](tasks/US-WNE-18-2.md) | Test: wg_recv copies data from smoltcp socket receive buffer to caller buffer and returns bytes actually received | ✅ done | — |  | — | US-WNE-18-7 | [US-WNE-18](stories/US-WNE-18.md) |
| [US-WNE-18-3](tasks/US-WNE-18-3.md) | Test: Both functions handle partial transfers by returning the actual byte count transferred | ✅ done | — |  | — | US-WNE-18-6 | [US-WNE-18](stories/US-WNE-18.md) |
| [US-WNE-18-4](tasks/US-WNE-18-4.md) | Test: WG_ERR_WOULD_BLOCK is returned when the socket is not ready for send or receive | ✅ done | — |  | — | US-WNE-18-6 | [US-WNE-18](stories/US-WNE-18.md) |
| [US-WNE-18-5](tasks/US-WNE-18-5.md) | Test: Null buffer pointer or zero length is handled safely returning appropriate error code | ✅ done | — |  | — | US-WNE-18-6 | [US-WNE-18](stories/US-WNE-18.md) |
| [US-WNE-18-6](tasks/US-WNE-18-6.md) | Implement wg_send for writing data to a socket | ✅ done | 2 |  | claude | — | [US-WNE-18](stories/US-WNE-18.md) |
| [US-WNE-18-7](tasks/US-WNE-18-7.md) | Implement wg_recv for reading data from a socket | ✅ done | 2 |  | claude | US-WNE-18-6 | [US-WNE-18](stories/US-WNE-18.md) |
| [US-WNE-18-8](tasks/US-WNE-18-8.md) | Test send/recv: full transfer, partial transfer, would-block, null buffer, closed socket | ✅ done | 2 |  | claude | US-WNE-18-6, US-WNE-18-7 | [US-WNE-18](stories/US-WNE-18.md) |
| [US-WNE-19-1](tasks/US-WNE-19-1.md) | Test: wg_get_stats populates a caller-provided WgStats struct with tunnel statistics including handshake age and byte... | ✅ done | — |  | — | — | [US-WNE-19](stories/US-WNE-19.md) |
| [US-WNE-19-2](tasks/US-WNE-19-2.md) | Test: Stats struct is C-compatible with repr(C) layout | ✅ done | — |  | — | — | [US-WNE-19](stories/US-WNE-19.md) |
| [US-WNE-19-3](tasks/US-WNE-19-3.md) | Test: wg_last_error returns a null-terminated error string for the most recent error on the calling thread (shared im... | ✅ done | — |  | — | — | [US-WNE-19](stories/US-WNE-19.md) |
| [US-WNE-19-4](tasks/US-WNE-19-4.md) | Define WgStats repr(C) struct and implement wg_get_stats | ✅ done | 2 |  | — | — | [US-WNE-19](stories/US-WNE-19.md) |
| [US-WNE-19-5](tasks/US-WNE-19-5.md) | Test wg_get_stats: valid stats, null pointer, invalid handle | ✅ done | 1 |  | — | US-WNE-19-4 | [US-WNE-19](stories/US-WNE-19.md) |
| [US-WNE-2-1](tasks/US-WNE-2-1.md) | Test: WgConfig struct with private_key listen_port and address fields | ✅ done | 1 |  | claude | US-WNE-2-5 | [US-WNE-2](stories/US-WNE-2.md) |
| [US-WNE-2-2](tasks/US-WNE-2-2.md) | Test: WgPeerConfig struct with public_key endpoint allowed_ips preshared_key and persistent_keepalive fields | ✅ done | 1 |  | claude | US-WNE-2-5 | [US-WNE-2](stories/US-WNE-2.md) |
| [US-WNE-2-3](tasks/US-WNE-2-3.md) | Test: All key fields use fixed-size byte arrays ([u8; 32]) not Strings | ✅ done | 1 |  | claude | US-WNE-2-5 | [US-WNE-2](stories/US-WNE-2.md) |
| [US-WNE-2-4](tasks/US-WNE-2-4.md) | Test: Config structs derive Clone and Debug with key fields redacted in Debug output | ✅ done | 1 |  | claude | US-WNE-2-5, US-WNE-2-6 | [US-WNE-2](stories/US-WNE-2.md) |
| [US-WNE-2-5](tasks/US-WNE-2-5.md) | Define WgConfig and WgPeerConfig structs | ✅ done | 1 |  | claude | — | [US-WNE-2](stories/US-WNE-2.md) |
| [US-WNE-2-6](tasks/US-WNE-2-6.md) | Implement custom Debug for key redaction | ✅ done | 1 |  | claude | US-WNE-2-5 | [US-WNE-2](stories/US-WNE-2.md) |
| [US-WNE-2-7](tasks/US-WNE-2-7.md) | Define ConfigError enum | ✅ done | 1 |  | claude | — | [US-WNE-2](stories/US-WNE-2.md) |
| [US-WNE-2-8](tasks/US-WNE-2-8.md) | Tests for config data model | ✅ done | 1 |  | claude | US-WNE-2-5, US-WNE-2-6, US-WNE-2-7 | [US-WNE-2](stories/US-WNE-2.md) |
| [US-WNE-20-1](tasks/US-WNE-20-1.md) | Test: WgDevice(WgConfig config) creates tunnel via native FFI layer | ✅ done | 2 |  | claude | — | [US-WNE-20](stories/US-WNE-20.md) |
| [US-WNE-20-10](tasks/US-WNE-20-10.md) | Test WgDevice lifecycle, ref-counting, and stats | ✅ done | 2 |  | claude | US-WNE-20-7, US-WNE-20-8, US-WNE-20-9 | [US-WNE-20](stories/US-WNE-20.md) |
| [US-WNE-20-2](tasks/US-WNE-20-2.md) | Test: Implements IDisposable and IAsyncDisposable for deterministic cleanup | ✅ done | 2 |  | claude | — | [US-WNE-20](stories/US-WNE-20.md) |
| [US-WNE-20-3](tasks/US-WNE-20-3.md) | Test: CreateSocket() factory returns new WgSocket.Socket bound to this device | ✅ done | 2 |  | claude | — | [US-WNE-20](stories/US-WNE-20.md) |
| [US-WNE-20-4](tasks/US-WNE-20-4.md) | Test: GetStats() returns tunnel health metrics (bytes tx/rx and handshake time and peer status) | ✅ done | 2 |  | claude | — | [US-WNE-20](stories/US-WNE-20.md) |
| [US-WNE-20-5](tasks/US-WNE-20-5.md) | Test: Ref-counting prevents disposal while sockets are still live | ✅ done | 2 |  | claude | — | [US-WNE-20](stories/US-WNE-20.md) |
| [US-WNE-20-6](tasks/US-WNE-20-6.md) | Test: Finalizer as safety net logs warning if Dispose was not called | ✅ done | 2 |  | claude | — | [US-WNE-20](stories/US-WNE-20.md) |
| [US-WNE-20-7](tasks/US-WNE-20-7.md) | Implement WgDevice constructor and tunnel creation | ✅ done | 2 |  | claude | — | [US-WNE-20](stories/US-WNE-20.md) |
| [US-WNE-20-8](tasks/US-WNE-20-8.md) | Implement WgDevice IDisposable, IAsyncDisposable, and ref-counting | ✅ done | 2 |  | claude | US-WNE-20-7 | [US-WNE-20](stories/US-WNE-20.md) |
| [US-WNE-20-9](tasks/US-WNE-20-9.md) | Implement WgDevice.CreateSocket() and GetStats() | ✅ done | 1 |  | claude | US-WNE-20-8 | [US-WNE-20](stories/US-WNE-20.md) |
| [US-WNE-21-1](tasks/US-WNE-21-1.md) | Test: cbindgen.toml is configured for C-style header output with appropriate include guard and language setting | ✅ done | — |  | — | — | [US-WNE-21](stories/US-WNE-21.md) |
| [US-WNE-21-2](tasks/US-WNE-21-2.md) | Test: build.rs invokes cbindgen to generate wgsocket.h during cargo build | ✅ done | — |  | — | — | [US-WNE-21](stories/US-WNE-21.md) |
| [US-WNE-21-3](tasks/US-WNE-21-3.md) | Test: Generated header includes all extern C function declarations and error code constants and struct definitions | ✅ done | — |  | — | — | [US-WNE-21](stories/US-WNE-21.md) |
| [US-WNE-21-4](tasks/US-WNE-21-4.md) | Test: wgsocket.h is checked into the repository at a well-known path (include/wgsocket.h) | ✅ done | — |  | — | — | [US-WNE-21](stories/US-WNE-21.md) |
| [US-WNE-21-5](tasks/US-WNE-21-5.md) | Test: CI step can diff-check the committed header against a freshly generated one to detect staleness | ✅ done | — |  | — | — | [US-WNE-21](stories/US-WNE-21.md) |
| [US-WNE-21-6](tasks/US-WNE-21-6.md) | Create cbindgen.toml and build.rs integration | ✅ done | 2 |  | claude | — | [US-WNE-21](stories/US-WNE-21.md) |
| [US-WNE-21-7](tasks/US-WNE-21-7.md) | Commit generated header and add CI staleness check | ✅ done | 1 |  | claude | US-WNE-21-6 | [US-WNE-21](stories/US-WNE-21.md) |
| [US-WNE-21-8](tasks/US-WNE-21-8.md) | Test cbindgen output: verify header contains expected symbols | ✅ done | 1 |  | claude | US-WNE-21-6 | [US-WNE-21](stories/US-WNE-21.md) |
| [US-WNE-22-1](tasks/US-WNE-22-1.md) | Test: Connect(IPEndPoint) initiates TCP connection through the WireGuard tunnel | ✅ done | 2 |  | claude | — | [US-WNE-22](stories/US-WNE-22.md) |
| [US-WNE-22-10](tasks/US-WNE-22-10.md) | Implement Socket.Connect and Socket.Bind | ✅ done | 2 |  | claude | US-WNE-22-9 | [US-WNE-22](stories/US-WNE-22.md) |
| [US-WNE-22-11](tasks/US-WNE-22-11.md) | Implement Socket.Listen and Socket.Accept | ✅ done | 2 |  | claude | US-WNE-22-9 | [US-WNE-22](stories/US-WNE-22.md) |
| [US-WNE-22-12](tasks/US-WNE-22-12.md) | Implement Socket.Send and Socket.Receive | ✅ done | 2 |  | claude | US-WNE-22-9 | [US-WNE-22](stories/US-WNE-22.md) |
| [US-WNE-22-13](tasks/US-WNE-22-13.md) | Implement Socket.Close and Dispose | ✅ done | 1 |  | claude | US-WNE-22-9 | [US-WNE-22](stories/US-WNE-22.md) |
| [US-WNE-22-14](tasks/US-WNE-22-14.md) | Test Socket synchronous API end-to-end | ✅ done | 3 |  | claude | US-WNE-22-10, US-WNE-22-11, US-WNE-22-12, US-WNE-22-13 | [US-WNE-22](stories/US-WNE-22.md) |
| [US-WNE-22-2](tasks/US-WNE-22-2.md) | Test: Bind(IPEndPoint) binds to a tunnel address | ✅ done | 2 |  | claude | — | [US-WNE-22](stories/US-WNE-22.md) |
| [US-WNE-22-3](tasks/US-WNE-22-3.md) | Test: Listen(int backlog) starts listening for incoming connections | ✅ done | 2 |  | claude | — | [US-WNE-22](stories/US-WNE-22.md) |
| [US-WNE-22-4](tasks/US-WNE-22-4.md) | Test: Accept() returns new Socket for each accepted connection | ✅ done | 2 |  | claude | — | [US-WNE-22](stories/US-WNE-22.md) |
| [US-WNE-22-5](tasks/US-WNE-22-5.md) | Test: Send(ReadOnlySpan<byte>) sends data and returns bytes sent | ✅ done | 1 |  | claude | — | [US-WNE-22](stories/US-WNE-22.md) |
| [US-WNE-22-6](tasks/US-WNE-22-6.md) | Test: Receive(Span<byte>) receives data and returns bytes received | ✅ done | 2 |  | claude | — | [US-WNE-22](stories/US-WNE-22.md) |
| [US-WNE-22-7](tasks/US-WNE-22-7.md) | Test: Close() and Dispose() release native and managed resources | ✅ done | 2 |  | claude | — | [US-WNE-22](stories/US-WNE-22.md) |
| [US-WNE-22-8](tasks/US-WNE-22-8.md) | Test: Method signatures match System.Net.Sockets.Socket as closely as possible | ✅ done | 2 |  | claude | — | [US-WNE-22](stories/US-WNE-22.md) |
| [US-WNE-22-9](tasks/US-WNE-22-9.md) | Implement Socket class scaffold and constructor | ✅ done | 2 |  | claude | — | [US-WNE-22](stories/US-WNE-22.md) |
| [US-WNE-23-1](tasks/US-WNE-23-1.md) | Test: Test valid wg.conf with single peer | ✅ done | 1 |  | claude | — | [US-WNE-23](stories/US-WNE-23.md) |
| [US-WNE-23-10](tasks/US-WNE-23-10.md) | Create config test fixtures and helper module | ✅ done | 2 |  | claude | — | [US-WNE-23](stories/US-WNE-23.md) |
| [US-WNE-23-11](tasks/US-WNE-23-11.md) | Implement config parsing happy-path tests | ✅ done | 2 |  | claude | US-WNE-23-10 | [US-WNE-23](stories/US-WNE-23.md) |
| [US-WNE-23-12](tasks/US-WNE-23-12.md) | Implement config parsing error-path tests | ✅ done | 1 |  | claude | US-WNE-23-10 | [US-WNE-23](stories/US-WNE-23.md) |
| [US-WNE-23-2](tasks/US-WNE-23-2.md) | Test: Test valid wg.conf with multiple peers | ✅ done | 1 |  | claude | — | [US-WNE-23](stories/US-WNE-23.md) |
| [US-WNE-23-3](tasks/US-WNE-23-3.md) | Test: Test all optional fields (PresharedKey PersistentKeepalive DNS) | ✅ done | 2 |  | claude | — | [US-WNE-23](stories/US-WNE-23.md) |
| [US-WNE-23-4](tasks/US-WNE-23-4.md) | Test: Test malformed base64 keys (wrong length and invalid chars) | ✅ done | 1 |  | claude | — | [US-WNE-23](stories/US-WNE-23.md) |
| [US-WNE-23-5](tasks/US-WNE-23-5.md) | Test: Test invalid CIDR (missing prefix and out of range) | ✅ done | 1 |  | claude | — | [US-WNE-23](stories/US-WNE-23.md) |
| [US-WNE-23-6](tasks/US-WNE-23-6.md) | Test: Test malformed endpoints | ✅ done | 1 |  | claude | — | [US-WNE-23](stories/US-WNE-23.md) |
| [US-WNE-23-7](tasks/US-WNE-23-7.md) | Test: Test missing required fields | ✅ done | 2 |  | claude | — | [US-WNE-23](stories/US-WNE-23.md) |
| [US-WNE-23-8](tasks/US-WNE-23-8.md) | Test: Test comment and whitespace handling | ✅ done | 2 |  | claude | — | [US-WNE-23](stories/US-WNE-23.md) |
| [US-WNE-23-9](tasks/US-WNE-23-9.md) | Test: Test config builder produces equivalent output | ✅ done | 2 |  | claude | — | [US-WNE-23](stories/US-WNE-23.md) |
| [US-WNE-24-1](tasks/US-WNE-24-1.md) | Test: ConnectAsync(IPEndPoint and CancellationToken) returns ValueTask | ✅ done | 2 |  | claude | — | [US-WNE-24](stories/US-WNE-24.md) |
| [US-WNE-24-10](tasks/US-WNE-24-10.md) | Test Socket async API with cancellation | ✅ done | 3 |  | claude | US-WNE-24-7, US-WNE-24-8, US-WNE-24-9 | [US-WNE-24](stories/US-WNE-24.md) |
| [US-WNE-24-2](tasks/US-WNE-24-2.md) | Test: AcceptAsync(CancellationToken) returns ValueTask<Socket> | ✅ done | 2 |  | claude | — | [US-WNE-24](stories/US-WNE-24.md) |
| [US-WNE-24-3](tasks/US-WNE-24-3.md) | Test: SendAsync(ReadOnlyMemory<byte> and CancellationToken) returns ValueTask<int> | ✅ done | 2 |  | claude | — | [US-WNE-24](stories/US-WNE-24.md) |
| [US-WNE-24-4](tasks/US-WNE-24-4.md) | Test: ReceiveAsync(Memory<byte> and CancellationToken) returns ValueTask<int> | ✅ done | 2 |  | claude | — | [US-WNE-24](stories/US-WNE-24.md) |
| [US-WNE-24-5](tasks/US-WNE-24-5.md) | Test: All async methods honor CancellationToken for cooperative cancellation | ✅ done | 2 |  | claude | — | [US-WNE-24](stories/US-WNE-24.md) |
| [US-WNE-24-6](tasks/US-WNE-24-6.md) | Test: Async methods do not block threadpool threads (truly async via native callbacks) | ✅ done | 2 |  | claude | — | [US-WNE-24](stories/US-WNE-24.md) |
| [US-WNE-24-7](tasks/US-WNE-24-7.md) | Implement ConnectAsync and AcceptAsync | ✅ done | 3 |  | claude | — | [US-WNE-24](stories/US-WNE-24.md) |
| [US-WNE-24-8](tasks/US-WNE-24-8.md) | Implement SendAsync and ReceiveAsync | ✅ done | 3 |  | claude | — | [US-WNE-24](stories/US-WNE-24.md) |
| [US-WNE-24-9](tasks/US-WNE-24-9.md) | Implement async cancellation and timeout support | ✅ done | 2 |  | claude | US-WNE-24-7, US-WNE-24-8 | [US-WNE-24](stories/US-WNE-24.md) |
| [US-WNE-25-1](tasks/US-WNE-25-1.md) | Test: Test boringtun encrypt produces valid WireGuard transport messages | ✅ done | 2 |  | claude | — | [US-WNE-25](stories/US-WNE-25.md) |
| [US-WNE-25-10](tasks/US-WNE-25-10.md) | Implement WireGuard message format and handshake tests | ✅ done | 2 |  | claude | US-WNE-25-9 | [US-WNE-25](stories/US-WNE-25.md) |
| [US-WNE-25-11](tasks/US-WNE-25-11.md) | Implement encrypt/decrypt roundtrip and crypto property tests | ✅ done | 3 |  | claude | US-WNE-25-9 | [US-WNE-25](stories/US-WNE-25.md) |
| [US-WNE-25-2](tasks/US-WNE-25-2.md) | Test: Test boringtun decrypt recovers original plaintext | ✅ done | 2 |  | claude | — | [US-WNE-25](stories/US-WNE-25.md) |
| [US-WNE-25-3](tasks/US-WNE-25-3.md) | Test: Test encrypt-then-decrypt roundtrip preserves data | ✅ done | 2 |  | claude | — | [US-WNE-25](stories/US-WNE-25.md) |
| [US-WNE-25-4](tasks/US-WNE-25-4.md) | Test: Test handshake initiation message format | ✅ done | 2 |  | claude | — | [US-WNE-25](stories/US-WNE-25.md) |
| [US-WNE-25-5](tasks/US-WNE-25-5.md) | Test: Test handshake response message format | ✅ done | 2 |  | claude | — | [US-WNE-25](stories/US-WNE-25.md) |
| [US-WNE-25-6](tasks/US-WNE-25-6.md) | Test: Test anti-replay (duplicate nonce rejected) | ✅ done | 2 |  | claude | — | [US-WNE-25](stories/US-WNE-25.md) |
| [US-WNE-25-7](tasks/US-WNE-25-7.md) | Test: Test timer-driven rekey produces new session | ✅ done | 2 |  | claude | — | [US-WNE-25](stories/US-WNE-25.md) |
| [US-WNE-25-8](tasks/US-WNE-25-8.md) | Test: Test keepalive packets generated correctly | ✅ done | 2 |  | claude | — | [US-WNE-25](stories/US-WNE-25.md) |
| [US-WNE-25-9](tasks/US-WNE-25-9.md) | Create boringtun test harness with paired tunnels | ✅ done | 3 |  | claude | — | [US-WNE-25](stories/US-WNE-25.md) |
| [US-WNE-26-1](tasks/US-WNE-26-1.md) | Test: NetworkStream(Socket socket) constructor wraps a WgSocket.Socket | ✅ done | 1 |  | claude | — | [US-WNE-26](stories/US-WNE-26.md) |
| [US-WNE-26-10](tasks/US-WNE-26-10.md) | Test NetworkStream with mock socket and framework compatibility | ✅ done | 2 |  | claude | US-WNE-26-7, US-WNE-26-8, US-WNE-26-9 | [US-WNE-26](stories/US-WNE-26.md) |
| [US-WNE-26-2](tasks/US-WNE-26-2.md) | Test: Inherits from System.IO.Stream | ✅ done | 1 |  | claude | — | [US-WNE-26](stories/US-WNE-26.md) |
| [US-WNE-26-3](tasks/US-WNE-26-3.md) | Test: Read/Write/ReadAsync/WriteAsync delegate to underlying socket Send/Receive methods | ✅ done | 2 |  | claude | — | [US-WNE-26](stories/US-WNE-26.md) |
| [US-WNE-26-4](tasks/US-WNE-26-4.md) | Test: CanRead/CanWrite/CanSeek report correctly (CanSeek is false) | ✅ done | 1 |  | claude | — | [US-WNE-26](stories/US-WNE-26.md) |
| [US-WNE-26-5](tasks/US-WNE-26-5.md) | Test: Disposing NetworkStream optionally disposes underlying socket (ownsSocket parameter) | ✅ done | 2 |  | claude | — | [US-WNE-26](stories/US-WNE-26.md) |
| [US-WNE-26-6](tasks/US-WNE-26-6.md) | Test: Compatible with StreamReader/StreamWriter and ASP.NET Core and HttpClient | ✅ done | 2 |  | claude | — | [US-WNE-26](stories/US-WNE-26.md) |
| [US-WNE-26-7](tasks/US-WNE-26-7.md) | Implement NetworkStream class inheriting System.IO.Stream | ✅ done | 1 |  | claude | — | [US-WNE-26](stories/US-WNE-26.md) |
| [US-WNE-26-8](tasks/US-WNE-26-8.md) | Implement NetworkStream Read/Write and async variants | ✅ done | 2 |  | claude | US-WNE-26-7 | [US-WNE-26](stories/US-WNE-26.md) |
| [US-WNE-26-9](tasks/US-WNE-26-9.md) | Implement NetworkStream Dispose and ownership semantics | ✅ done | 1 |  | claude | US-WNE-26-7 | [US-WNE-26](stories/US-WNE-26.md) |
| [US-WNE-27-1](tasks/US-WNE-27-1.md) | Test: Test TCP socket open/bind/listen/accept on smoltcp interface | ✅ done | 2 |  | claude | — | [US-WNE-27](stories/US-WNE-27.md) |
| [US-WNE-27-10](tasks/US-WNE-27-10.md) | Implement UDP and concurrent socket tests | ✅ done | 2 |  | — | US-WNE-27-8 | [US-WNE-27](stories/US-WNE-27.md) |
| [US-WNE-27-2](tasks/US-WNE-27-2.md) | Test: Test TCP connect to listening socket (loopback) | ✅ done | 2 |  | claude | — | [US-WNE-27](stories/US-WNE-27.md) |
| [US-WNE-27-3](tasks/US-WNE-27-3.md) | Test: Test data send/receive through smoltcp TCP | ✅ done | 2 |  | claude | — | [US-WNE-27](stories/US-WNE-27.md) |
| [US-WNE-27-4](tasks/US-WNE-27-4.md) | Test: Test UDP socket send/receive | ✅ done | 2 |  | claude | — | [US-WNE-27](stories/US-WNE-27.md) |
| [US-WNE-27-5](tasks/US-WNE-27-5.md) | Test: Test socket buffer sizing | ✅ done | 2 |  | claude | — | [US-WNE-27](stories/US-WNE-27.md) |
| [US-WNE-27-6](tasks/US-WNE-27-6.md) | Test: Test multiple concurrent sockets on same interface | ✅ done | 2 |  | claude | — | [US-WNE-27](stories/US-WNE-27.md) |
| [US-WNE-27-7](tasks/US-WNE-27-7.md) | Test: Test socket close and resource cleanup | ✅ done | 2 |  | claude | — | [US-WNE-27](stories/US-WNE-27.md) |
| [US-WNE-27-8](tasks/US-WNE-27-8.md) | Create smoltcp test harness with loopback interface | ✅ done | 2 |  | claude | — | [US-WNE-27](stories/US-WNE-27.md) |
| [US-WNE-27-9](tasks/US-WNE-27-9.md) | Implement TCP socket lifecycle tests | ✅ done | 2 |  | — | US-WNE-27-8 | [US-WNE-27](stories/US-WNE-27.md) |
| [US-WNE-28-1](tasks/US-WNE-28-1.md) | Test: Each WgDevice spawns a dedicated I/O thread | ✅ done | 2 |  | claude | — | [US-WNE-28](stories/US-WNE-28.md) |
| [US-WNE-28-2](tasks/US-WNE-28-2.md) | Test: Poll loop checks real UDP socket for incoming packets using non-blocking I/O | ✅ done | 2 |  | claude | — | [US-WNE-28](stories/US-WNE-28.md) |
| [US-WNE-28-3](tasks/US-WNE-28-3.md) | Test: Poll loop drives smoltcp timers and outbound packet processing | ✅ done | 2 |  | claude | — | [US-WNE-28](stories/US-WNE-28.md) |
| [US-WNE-28-4](tasks/US-WNE-28-4.md) | Test: Thread shuts down cleanly when device is dropped | ✅ done | 2 |  | claude | — | [US-WNE-28](stories/US-WNE-28.md) |
| [US-WNE-28-5](tasks/US-WNE-28-5.md) | Test: Application threads interact via smoltcp socket buffers with thread-safe access | ✅ done | 2 |  | claude | — | [US-WNE-28](stories/US-WNE-28.md) |
| [US-WNE-28-6](tasks/US-WNE-28-6.md) | Implement I/O thread spawn and shutdown mechanism | ✅ done | 2 |  | claude | — | [US-WNE-28](stories/US-WNE-28.md) |
| [US-WNE-28-7](tasks/US-WNE-28-7.md) | Implement non-blocking poll loop with timer integration | ✅ done | 3 |  | claude | — | [US-WNE-28](stories/US-WNE-28.md) |
| [US-WNE-28-8](tasks/US-WNE-28-8.md) | Implement thread-safe socket buffer access for application threads | ✅ done | 2 |  | claude | — | [US-WNE-28](stories/US-WNE-28.md) |
| [US-WNE-28-9](tasks/US-WNE-28-9.md) | Test I/O thread lifecycle and thread-safe socket access | ✅ done | 2 |  | claude | US-WNE-28-6, US-WNE-28-7, US-WNE-28-8 | [US-WNE-28](stories/US-WNE-28.md) |
| [US-WNE-29-1](tasks/US-WNE-29-1.md) | Test: Connected property reflects current connection state | ✅ done | 1 |  | claude | — | [US-WNE-29](stories/US-WNE-29.md) |
| [US-WNE-29-2](tasks/US-WNE-29-2.md) | Test: LocalEndPoint and RemoteEndPoint properties return correct IPEndPoints | ✅ done | 2 |  | claude | — | [US-WNE-29](stories/US-WNE-29.md) |
| [US-WNE-29-3](tasks/US-WNE-29-3.md) | Test: Available property reports bytes ready to read | ✅ done | 1 |  | claude | — | [US-WNE-29](stories/US-WNE-29.md) |
| [US-WNE-29-4](tasks/US-WNE-29-4.md) | Test: SocketType and ProtocolType properties expose socket configuration | ✅ done | 1 |  | claude | — | [US-WNE-29](stories/US-WNE-29.md) |
| [US-WNE-29-5](tasks/US-WNE-29-5.md) | Test: Blocking property toggles synchronous mode behavior | ✅ done | 2 |  | claude | — | [US-WNE-29](stories/US-WNE-29.md) |
| [US-WNE-29-6](tasks/US-WNE-29-6.md) | Test: State transitions validated with clear exceptions (e.g. cannot Send before Connect) | ✅ done | 2 |  | claude | — | [US-WNE-29](stories/US-WNE-29.md) |
| [US-WNE-29-7](tasks/US-WNE-29-7.md) | Implement Socket connection and endpoint properties | ✅ done | 1 |  | claude | — | [US-WNE-29](stories/US-WNE-29.md) |
| [US-WNE-29-8](tasks/US-WNE-29-8.md) | Implement Socket type properties and state machine | ✅ done | 2 |  | claude | — | [US-WNE-29](stories/US-WNE-29.md) |
| [US-WNE-29-9](tasks/US-WNE-29-9.md) | Test Socket properties and state transitions | ✅ done | 2 |  | claude | US-WNE-29-7, US-WNE-29-8 | [US-WNE-29](stories/US-WNE-29.md) |
| [US-WNE-3-1](tasks/US-WNE-3-1.md) | Test: Parses [Interface] section including PrivateKey ListenPort Address and DNS fields | ✅ done | 1 |  | claude | US-WNE-3-7, US-WNE-3-9 | [US-WNE-3](stories/US-WNE-3.md) |
| [US-WNE-3-10](tasks/US-WNE-3-10.md) | Tests for wg.conf parser | ✅ done | 2 |  | claude | US-WNE-3-6, US-WNE-3-7, US-WNE-3-8, US-WNE-3-9 | [US-WNE-3](stories/US-WNE-3.md) |
| [US-WNE-3-2](tasks/US-WNE-3-2.md) | Test: Parses [Peer] sections including PublicKey Endpoint AllowedIPs PresharedKey and PersistentKeepalive fields | ✅ done | 1 |  | claude | US-WNE-3-8, US-WNE-3-9 | [US-WNE-3](stories/US-WNE-3.md) |
| [US-WNE-3-3](tasks/US-WNE-3-3.md) | Test: Handles multiple [Peer] sections in a single config file | ✅ done | 1 |  | claude | US-WNE-3-8, US-WNE-3-9 | [US-WNE-3](stories/US-WNE-3.md) |
| [US-WNE-3-4](tasks/US-WNE-3-4.md) | Test: Ignores comments (# lines) and blank lines | ✅ done | 1 |  | claude | US-WNE-3-6 | [US-WNE-3](stories/US-WNE-3.md) |
| [US-WNE-3-5](tasks/US-WNE-3-5.md) | Test: Returns descriptive error messages for malformed input including line numbers | ✅ done | 1 |  | claude | US-WNE-3-9 | [US-WNE-3](stories/US-WNE-3.md) |
| [US-WNE-3-6](tasks/US-WNE-3-6.md) | Implement INI-style line tokenizer | ✅ done | 1 |  | claude | — | [US-WNE-3](stories/US-WNE-3.md) |
| [US-WNE-3-7](tasks/US-WNE-3-7.md) | Implement Interface section parser | ✅ done | 1 |  | claude | US-WNE-3-6 | [US-WNE-3](stories/US-WNE-3.md) |
| [US-WNE-3-8](tasks/US-WNE-3-8.md) | Implement Peer section parser | ✅ done | 1 |  | claude | US-WNE-3-6 | [US-WNE-3](stories/US-WNE-3.md) |
| [US-WNE-3-9](tasks/US-WNE-3-9.md) | Implement WgConfig::from_str and from_file | ✅ done | 1 |  | claude | US-WNE-3-7, US-WNE-3-8 | [US-WNE-3](stories/US-WNE-3.md) |
| [US-WNE-30-1](tasks/US-WNE-30-1.md) | Test: Test full outbound path (app data to smoltcp to boringtun to encrypted packet) | ⚪ todo | 1 |  | — | US-WNE-30-9 | [US-WNE-30](stories/US-WNE-30.md) |
| [US-WNE-30-10](tasks/US-WNE-30-10.md) | Implement fragmentation and concurrency integration tests | ✅ done | 3 |  | claude | US-WNE-30-8 | [US-WNE-30](stories/US-WNE-30.md) |
| [US-WNE-30-2](tasks/US-WNE-30-2.md) | Test: Test full inbound path (encrypted packet to boringtun to smoltcp to app data) | ⚪ todo | 1 |  | — | US-WNE-30-9 | [US-WNE-30](stories/US-WNE-30.md) |
| [US-WNE-30-3](tasks/US-WNE-30-3.md) | Test: Test bidirectional data flow through two paired tunnels | ⚪ todo | 1 |  | — | US-WNE-30-9 | [US-WNE-30](stories/US-WNE-30.md) |
| [US-WNE-30-4](tasks/US-WNE-30-4.md) | Test: Test handshake completes between two tunnel instances | ✅ done | 1 |  | claude | US-WNE-30-8 | [US-WNE-30](stories/US-WNE-30.md) |
| [US-WNE-30-5](tasks/US-WNE-30-5.md) | Test: Test data flows after successful handshake | ✅ done | 1 |  | claude | US-WNE-30-8 | [US-WNE-30](stories/US-WNE-30.md) |
| [US-WNE-30-6](tasks/US-WNE-30-6.md) | Test: Test large payload (>MTU) fragmentation and reassembly | ✅ done | 1 |  | claude | US-WNE-30-10 | [US-WNE-30](stories/US-WNE-30.md) |
| [US-WNE-30-7](tasks/US-WNE-30-7.md) | Test: Test concurrent sends from multiple sockets | ✅ done | 1 |  | claude | US-WNE-30-10 | [US-WNE-30](stories/US-WNE-30.md) |
| [US-WNE-30-8](tasks/US-WNE-30-8.md) | Create integrated tunnel test harness (smoltcp + boringtun) | ✅ done | 3 |  | claude | — | [US-WNE-30](stories/US-WNE-30.md) |
| [US-WNE-30-9](tasks/US-WNE-30-9.md) | Implement end-to-end data path integration tests | ⚪ todo | 3 |  | claude | US-WNE-30-8 | [US-WNE-30](stories/US-WNE-30.md) |
| [US-WNE-31-1](tasks/US-WNE-31-1.md) | Test: Namespace is WgSocket (not WgSocket.Net or WgSocket.Sockets) | ✅ done | 1 |  | claude | — | [US-WNE-31](stories/US-WNE-31.md) |
| [US-WNE-31-2](tasks/US-WNE-31-2.md) | Test: using WgSocket gives access to Socket and WgDevice and WgConfig and WgPeer and NetworkStream | ✅ done | 1 |  | claude | — | [US-WNE-31](stories/US-WNE-31.md) |
| [US-WNE-31-3](tasks/US-WNE-31-3.md) | Test: No naming conflicts with System.Net.Sockets when both namespaces are imported | ✅ done | 1 |  | claude | — | [US-WNE-31](stories/US-WNE-31.md) |
| [US-WNE-31-4](tasks/US-WNE-31-4.md) | Test: IntelliSense-friendly API surface with XML doc comments on all public members | ✅ done | 1 |  | claude | — | [US-WNE-31](stories/US-WNE-31.md) |
| [US-WNE-31-5](tasks/US-WNE-31-5.md) | Configure namespace and verify public API surface | ✅ done | 1 |  | claude | — | [US-WNE-31](stories/US-WNE-31.md) |
| [US-WNE-31-6](tasks/US-WNE-31-6.md) | Test single-file import and namespace conflict scenarios | ✅ done | 1 |  | claude | US-WNE-31-5 | [US-WNE-31](stories/US-WNE-31.md) |
| [US-WNE-32-1](tasks/US-WNE-32-1.md) | Test: Test wg_device_new with valid config returns valid handle | ✅ done | 1 |  | claude | — | [US-WNE-32](stories/US-WNE-32.md) |
| [US-WNE-32-10](tasks/US-WNE-32-10.md) | Create FFI test harness with C-calling-convention helpers | ✅ done | 2 |  | claude | — | [US-WNE-32](stories/US-WNE-32.md) |
| [US-WNE-32-11](tasks/US-WNE-32-11.md) | Implement FFI valid-path and error-code tests | ✅ done | 2 |  | claude | US-WNE-32-10 | [US-WNE-32](stories/US-WNE-32.md) |
| [US-WNE-32-12](tasks/US-WNE-32-12.md) | Implement FFI null-pointer, double-free, and concurrency tests | ✅ done | 3 |  | claude | US-WNE-32-10 | [US-WNE-32](stories/US-WNE-32.md) |
| [US-WNE-32-2](tasks/US-WNE-32-2.md) | Test: Test wg_device_new with invalid config returns error code | ✅ done | 1 |  | claude | — | [US-WNE-32](stories/US-WNE-32.md) |
| [US-WNE-32-3](tasks/US-WNE-32-3.md) | Test: Test all functions with invalid handle return WG_ERR_INVALID_HANDLE | ✅ done | 2 |  | claude | — | [US-WNE-32](stories/US-WNE-32.md) |
| [US-WNE-32-4](tasks/US-WNE-32-4.md) | Test: Test wg_send/wg_recv with null buffer pointer | ✅ done | 1 |  | claude | — | [US-WNE-32](stories/US-WNE-32.md) |
| [US-WNE-32-5](tasks/US-WNE-32-5.md) | Test: Test wg_send/wg_recv with zero length | ✅ done | 1 |  | claude | — | [US-WNE-32](stories/US-WNE-32.md) |
| [US-WNE-32-6](tasks/US-WNE-32-6.md) | Test: Test double wg_device_free (safe and returns error) | ✅ done | 2 |  | claude | — | [US-WNE-32](stories/US-WNE-32.md) |
| [US-WNE-32-7](tasks/US-WNE-32-7.md) | Test: Test double wg_close (safe and returns error) | ✅ done | 2 |  | claude | — | [US-WNE-32](stories/US-WNE-32.md) |
| [US-WNE-32-8](tasks/US-WNE-32-8.md) | Test: Test concurrent FFI calls from multiple threads | ✅ done | 2 |  | claude | — | [US-WNE-32](stories/US-WNE-32.md) |
| [US-WNE-32-9](tasks/US-WNE-32-9.md) | Test: Test wg_last_error returns correct error string | ✅ done | 1 |  | claude | — | [US-WNE-32](stories/US-WNE-32.md) |
| [US-WNE-33-1](tasks/US-WNE-33-1.md) | Test: Test WgConfig construction with valid parameters | ✅ done | 1 |  | claude | — | [US-WNE-33](stories/US-WNE-33.md) |
| [US-WNE-33-10](tasks/US-WNE-33-10.md) | Implement WgConfig and WgPeer happy-path construction tests | ✅ done | 1 |  | claude | US-WNE-33-9 | [US-WNE-33](stories/US-WNE-33.md) |
| [US-WNE-33-11](tasks/US-WNE-33-11.md) | Implement WgConfig and WgPeer validation rejection tests | ✅ done | 1 |  | claude | US-WNE-33-9 | [US-WNE-33](stories/US-WNE-33.md) |
| [US-WNE-33-12](tasks/US-WNE-33-12.md) | Implement ToString redaction and builder pattern tests | ✅ done | 1 |  | claude | US-WNE-33-9 | [US-WNE-33](stories/US-WNE-33.md) |
| [US-WNE-33-2](tasks/US-WNE-33-2.md) | Test: Test WgPeer construction with valid parameters | ✅ done | 1 |  | claude | — | [US-WNE-33](stories/US-WNE-33.md) |
| [US-WNE-33-3](tasks/US-WNE-33-3.md) | Test: Test validation rejects null/empty private key | ✅ done | 1 |  | claude | — | [US-WNE-33](stories/US-WNE-33.md) |
| [US-WNE-33-4](tasks/US-WNE-33-4.md) | Test: Test validation rejects invalid key length | ✅ done | 1 |  | claude | — | [US-WNE-33](stories/US-WNE-33.md) |
| [US-WNE-33-5](tasks/US-WNE-33-5.md) | Test: Test validation rejects invalid endpoint format | ✅ done | 1 |  | claude | — | [US-WNE-33](stories/US-WNE-33.md) |
| [US-WNE-33-6](tasks/US-WNE-33-6.md) | Test: Test validation rejects invalid CIDR in AllowedIPs | ✅ done | 1 |  | claude | — | [US-WNE-33](stories/US-WNE-33.md) |
| [US-WNE-33-7](tasks/US-WNE-33-7.md) | Test: Test ToString() redacts key material (never shows private key or PSK) | ✅ done | 2 |  | claude | — | [US-WNE-33](stories/US-WNE-33.md) |
| [US-WNE-33-8](tasks/US-WNE-33-8.md) | Test: Test builder/initializer pattern works correctly | ✅ done | 1 |  | claude | — | [US-WNE-33](stories/US-WNE-33.md) |
| [US-WNE-33-9](tasks/US-WNE-33-9.md) | Scaffold WgConfigTests and WgPeerTests test classes | ✅ done | 1 |  | claude | — | [US-WNE-33](stories/US-WNE-33.md) |
| [US-WNE-34-1](tasks/US-WNE-34-1.md) | Test: Test device free releases all sockets | ✅ done | 2 |  | claude | — | [US-WNE-34](stories/US-WNE-34.md) |
| [US-WNE-34-2](tasks/US-WNE-34-2.md) | Test: Test no memory leaks after create/use/free cycle (valgrind or similar) | ✅ done | 2 |  | claude | — | [US-WNE-34](stories/US-WNE-34.md) |
| [US-WNE-34-3](tasks/US-WNE-34-3.md) | Test: Test key material is zeroed after device free | ✅ done | 2 |  | claude | — | [US-WNE-34](stories/US-WNE-34.md) |
| [US-WNE-34-4](tasks/US-WNE-34-4.md) | Test: Test I/O thread terminates after device free | ✅ done | 2 |  | claude | — | [US-WNE-34](stories/US-WNE-34.md) |
| [US-WNE-34-5](tasks/US-WNE-34-5.md) | Test: Test handle map doesn't grow unboundedly after repeated create/free | ✅ done | 2 |  | claude | — | [US-WNE-34](stories/US-WNE-34.md) |
| [US-WNE-34-6](tasks/US-WNE-34-6.md) | Implement socket and resource release tests | ✅ done | 2 |  | claude | — | [US-WNE-34](stories/US-WNE-34.md) |
| [US-WNE-34-7](tasks/US-WNE-34-7.md) | Implement memory leak and key-zeroization tests | ✅ done | 3 |  | claude | US-WNE-34-6 | [US-WNE-34](stories/US-WNE-34.md) |
| [US-WNE-35-1](tasks/US-WNE-35-1.md) | Test: Device instances stored in a global handle map with opaque usize handles | ✅ done | 2 |  | claude | — | [US-WNE-35](stories/US-WNE-35.md) |
| [US-WNE-35-2](tasks/US-WNE-35-2.md) | Test: Handles are validated on every FFI entry point | ✅ done | 2 |  | claude | — | [US-WNE-35](stories/US-WNE-35.md) |
| [US-WNE-35-3](tasks/US-WNE-35-3.md) | Test: Invalid handles return error codes and do not crash | ✅ done | 2 |  | claude | — | [US-WNE-35](stories/US-WNE-35.md) |
| [US-WNE-35-4](tasks/US-WNE-35-4.md) | Test: Ref-counting prevents device teardown while sockets are live | ✅ done | 2 |  | claude | — | [US-WNE-35](stories/US-WNE-35.md) |
| [US-WNE-35-5](tasks/US-WNE-35-5.md) | Test: Device cleanup zeroes sensitive memory (keys and session state) | ✅ done | 2 |  | claude | — | [US-WNE-35](stories/US-WNE-35.md) |
| [US-WNE-35-6](tasks/US-WNE-35-6.md) | Implement global handle map with opaque usize handles | ✅ done | 2 |  | claude | — | [US-WNE-35](stories/US-WNE-35.md) |
| [US-WNE-35-7](tasks/US-WNE-35-7.md) | Implement handle validation, ref-counting, and secure cleanup | ✅ done | 2 |  | claude | — | [US-WNE-35](stories/US-WNE-35.md) |
| [US-WNE-35-8](tasks/US-WNE-35-8.md) | Test handle map safety and secure memory cleanup | ✅ done | 2 |  | claude | US-WNE-35-6, US-WNE-35-7 | [US-WNE-35](stories/US-WNE-35.md) |
| [US-WNE-36-1](tasks/US-WNE-36-1.md) | Test: Helper generates Curve25519 keypairs for tests | ✅ done | — |  | — | — | [US-WNE-36](stories/US-WNE-36.md) |
| [US-WNE-36-10](tasks/US-WNE-36-10.md) | Implement xUnit collection fixture and CI port allocation | ✅ done | 2 |  | claude | — | [US-WNE-36](stories/US-WNE-36.md) |
| [US-WNE-36-11](tasks/US-WNE-36-11.md) | Test: Verify test harness creates functional paired tunnel | ✅ done | 2 |  | claude | US-WNE-36-7, US-WNE-36-8, US-WNE-36-9, US-WNE-36-10 | [US-WNE-36](stories/US-WNE-36.md) |
| [US-WNE-36-2](tasks/US-WNE-36-2.md) | Test: Helper creates two WgDevice instances configured as peers (localhost UDP different ports) | ✅ done | — |  | — | — | [US-WNE-36](stories/US-WNE-36.md) |
| [US-WNE-36-3](tasks/US-WNE-36-3.md) | Test: Helper waits for handshake completion with configurable timeout | ✅ done | — |  | — | — | [US-WNE-36](stories/US-WNE-36.md) |
| [US-WNE-36-4](tasks/US-WNE-36-4.md) | Test: Helper provides cleanup/disposal via IAsyncDisposable | ✅ done | — |  | — | — | [US-WNE-36](stories/US-WNE-36.md) |
| [US-WNE-36-5](tasks/US-WNE-36-5.md) | Test: Works in CI with no network access needed beyond localhost | ✅ done | — |  | — | — | [US-WNE-36](stories/US-WNE-36.md) |
| [US-WNE-36-6](tasks/US-WNE-36-6.md) | Test: Harness exposes tunnel IPs and ports for test assertions | ✅ done | — |  | — | — | [US-WNE-36](stories/US-WNE-36.md) |
| [US-WNE-36-7](tasks/US-WNE-36-7.md) | Implement WgTestKeypair helper for Curve25519 key generation | ✅ done | 1 |  | claude | — | [US-WNE-36](stories/US-WNE-36.md) |
| [US-WNE-36-8](tasks/US-WNE-36-8.md) | Implement WgTunnelPair test fixture for paired WgDevice creation | ✅ done | 2 |  | claude | — | [US-WNE-36](stories/US-WNE-36.md) |
| [US-WNE-36-9](tasks/US-WNE-36-9.md) | Implement handshake wait and health check in test harness | ✅ done | 2 |  | claude | — | [US-WNE-36](stories/US-WNE-36.md) |
| [US-WNE-37-1](tasks/US-WNE-37-1.md) | Test: Test NativeMethods declarations compile and link correctly | ✅ done | 2 |  | claude | — | [US-WNE-37](stories/US-WNE-37.md) |
| [US-WNE-37-10](tasks/US-WNE-37-10.md) | Implement return code handling and wg_last_error tests | ✅ done | 2 |  | claude | US-WNE-37-7 | [US-WNE-37](stories/US-WNE-37.md) |
| [US-WNE-37-2](tasks/US-WNE-37-2.md) | Test: Test string marshalling (UTF-8 and null terminator) | ✅ done | 2 |  | claude | — | [US-WNE-37](stories/US-WNE-37.md) |
| [US-WNE-37-3](tasks/US-WNE-37-3.md) | Test: Test buffer pinning during P/Invoke calls | ✅ done | 1 |  | claude | — | [US-WNE-37](stories/US-WNE-37.md) |
| [US-WNE-37-4](tasks/US-WNE-37-4.md) | Test: Test ReadOnlySpan<byte> key parameter marshalling | ✅ done | 2 |  | claude | — | [US-WNE-37](stories/US-WNE-37.md) |
| [US-WNE-37-5](tasks/US-WNE-37-5.md) | Test: Test return code handling for all error codes | ✅ done | 2 |  | claude | — | [US-WNE-37](stories/US-WNE-37.md) |
| [US-WNE-37-6](tasks/US-WNE-37-6.md) | Test: Test wg_last_error string retrieval | ✅ done | 2 |  | claude | — | [US-WNE-37](stories/US-WNE-37.md) |
| [US-WNE-37-7](tasks/US-WNE-37-7.md) | Create INativeMethodsProxy interface and mock for P/Invoke testing | ✅ done | 2 |  | claude | — | [US-WNE-37](stories/US-WNE-37.md) |
| [US-WNE-37-8](tasks/US-WNE-37-8.md) | Implement NativeMethods declaration and string marshalling tests | ✅ done | 2 |  | claude | US-WNE-37-7 | [US-WNE-37](stories/US-WNE-37.md) |
| [US-WNE-37-9](tasks/US-WNE-37-9.md) | Implement buffer pinning and Span marshalling tests | ✅ done | 2 |  | claude | US-WNE-37-7 | [US-WNE-37](stories/US-WNE-37.md) |
| [US-WNE-38-1](tasks/US-WNE-38-1.md) | Test: Server device listens on tunnel IP and client device connects through tunnel | ✅ done | — |  | — | — | [US-WNE-38](stories/US-WNE-38.md) |
| [US-WNE-38-10](tasks/US-WNE-38-10.md) | Test: TCP echo roundtrip with small payloads (1 byte, 100 bytes) | ✅ done | 1 |  | claude | US-WNE-38-8, US-WNE-38-9 | [US-WNE-38](stories/US-WNE-38.md) |
| [US-WNE-38-11](tasks/US-WNE-38-11.md) | Test: TCP echo roundtrip with medium payloads (1KB, 64KB) | ✅ done | 2 |  | claude | US-WNE-38-8, US-WNE-38-9 | [US-WNE-38](stories/US-WNE-38.md) |
| [US-WNE-38-12](tasks/US-WNE-38-12.md) | Test: TCP echo roundtrip with large payloads (1MB) testing fragmentation | ✅ done | 2 |  | claude | US-WNE-38-8, US-WNE-38-9 | [US-WNE-38](stories/US-WNE-38.md) |
| [US-WNE-38-13](tasks/US-WNE-38-13.md) | Test: TCP echo via sync and async API paths | ✅ done | 2 |  | claude | US-WNE-38-8, US-WNE-38-9 | [US-WNE-38](stories/US-WNE-38.md) |
| [US-WNE-38-2](tasks/US-WNE-38-2.md) | Test: Client sends byte[] through tunnel and server echoes it back | ✅ done | — |  | — | — | [US-WNE-38](stories/US-WNE-38.md) |
| [US-WNE-38-3](tasks/US-WNE-38-3.md) | Test: Received data matches sent data exactly (byte-for-byte comparison) | ✅ done | — |  | — | — | [US-WNE-38](stories/US-WNE-38.md) |
| [US-WNE-38-4](tasks/US-WNE-38-4.md) | Test: Works with small payloads (1 byte and 100 bytes) | ✅ done | — |  | — | — | [US-WNE-38](stories/US-WNE-38.md) |
| [US-WNE-38-5](tasks/US-WNE-38-5.md) | Test: Works with medium payloads (1KB and 64KB) | ✅ done | — |  | — | — | [US-WNE-38](stories/US-WNE-38.md) |
| [US-WNE-38-6](tasks/US-WNE-38-6.md) | Test: Works with large payloads (1MB -- tests fragmentation and reassembly) | ✅ done | — |  | — | — | [US-WNE-38](stories/US-WNE-38.md) |
| [US-WNE-38-7](tasks/US-WNE-38-7.md) | Test: Test both sync and async API paths | ✅ done | — |  | — | — | [US-WNE-38](stories/US-WNE-38.md) |
| [US-WNE-38-8](tasks/US-WNE-38-8.md) | Implement TCP echo server helper for integration tests | ✅ done | 2 |  | claude | — | [US-WNE-38](stories/US-WNE-38.md) |
| [US-WNE-38-9](tasks/US-WNE-38-9.md) | Implement TCP echo client helper for integration tests | ✅ done | 1 |  | claude | — | [US-WNE-38](stories/US-WNE-38.md) |
| [US-WNE-39-1](tasks/US-WNE-39-1.md) | Test: Both peers send data simultaneously in both directions | ✅ done | — |  | — | — | [US-WNE-39](stories/US-WNE-39.md) |
| [US-WNE-39-2](tasks/US-WNE-39-2.md) | Test: Data integrity verified with no corruption and no mixing | ✅ done | — |  | — | — | [US-WNE-39](stories/US-WNE-39.md) |
| [US-WNE-39-3](tasks/US-WNE-39-3.md) | Test: Multiple concurrent sockets between same peers work correctly | ✅ done | — |  | — | — | [US-WNE-39](stories/US-WNE-39.md) |
| [US-WNE-39-4](tasks/US-WNE-39-4.md) | Test: Test under load with many small messages sent rapidly | ✅ done | — |  | — | — | [US-WNE-39](stories/US-WNE-39.md) |
| [US-WNE-39-5](tasks/US-WNE-39-5.md) | Test: All async operations complete without deadlock or timeout | ✅ done | — |  | — | — | [US-WNE-39](stories/US-WNE-39.md) |
| [US-WNE-39-6](tasks/US-WNE-39-6.md) | Implement bidirectional transfer test helper | ✅ done | 2 |  | claude | — | [US-WNE-39](stories/US-WNE-39.md) |
| [US-WNE-39-7](tasks/US-WNE-39-7.md) | Test: Simultaneous bidirectional TCP data transfer | ✅ done | 2 |  | claude | US-WNE-39-6 | [US-WNE-39](stories/US-WNE-39.md) |
| [US-WNE-39-8](tasks/US-WNE-39-8.md) | Test: Multiple concurrent sockets between same peers | ✅ done | 2 |  | claude | US-WNE-39-6 | [US-WNE-39](stories/US-WNE-39.md) |
| [US-WNE-39-9](tasks/US-WNE-39-9.md) | Test: Rapid small message stress test | ✅ done | 2 |  | claude | US-WNE-39-6 | [US-WNE-39](stories/US-WNE-39.md) |
| [US-WNE-4-1](tasks/US-WNE-4-1.md) | Test: Validates base64 key format and decoded length is exactly 32 bytes for Curve25519 keys | ✅ done | 1 |  | claude | US-WNE-4-6 | [US-WNE-4](stories/US-WNE-4.md) |
| [US-WNE-4-2](tasks/US-WNE-4-2.md) | Test: Validates CIDR notation in AllowedIPs (valid IP prefix and mask length) | ✅ done | 1 |  | claude | US-WNE-4-7 | [US-WNE-4](stories/US-WNE-4.md) |
| [US-WNE-4-3](tasks/US-WNE-4-3.md) | Test: Validates endpoint format (IP:port or hostname:port) | ✅ done | 1 |  | claude | US-WNE-4-7 | [US-WNE-4](stories/US-WNE-4.md) |
| [US-WNE-4-4](tasks/US-WNE-4-4.md) | Test: Rejects configs missing required fields (PrivateKey and at least one peer with PublicKey) | ✅ done | 1 |  | claude | US-WNE-4-8 | [US-WNE-4](stories/US-WNE-4.md) |
| [US-WNE-4-5](tasks/US-WNE-4-5.md) | Test: Validates listen port range (1-65535) | ✅ done | 1 |  | claude | US-WNE-4-7 | [US-WNE-4](stories/US-WNE-4.md) |
| [US-WNE-4-6](tasks/US-WNE-4-6.md) | Implement key validation (base64 + length) | ✅ done | 1 |  | claude | — | [US-WNE-4](stories/US-WNE-4.md) |
| [US-WNE-4-7](tasks/US-WNE-4-7.md) | Implement CIDR and endpoint validation | ✅ done | 2 |  | claude | — | [US-WNE-4](stories/US-WNE-4.md) |
| [US-WNE-4-8](tasks/US-WNE-4-8.md) | Implement full config validation pass | ✅ done | 2 |  | claude | US-WNE-4-6, US-WNE-4-7 | [US-WNE-4](stories/US-WNE-4.md) |
| [US-WNE-4-9](tasks/US-WNE-4-9.md) | Tests for config validation | ✅ done | 2 |  | claude | US-WNE-4-6, US-WNE-4-7, US-WNE-4-8 | [US-WNE-4](stories/US-WNE-4.md) |
| [US-WNE-40-1](tasks/US-WNE-40-1.md) | Test: Three or more WgDevice instances configured in a mesh or star topology | ✅ done | — |  | — | — | [US-WNE-40](stories/US-WNE-40.md) |
| [US-WNE-40-10](tasks/US-WNE-40-10.md) | Test: Clean teardown of multi-peer topology | ✅ done | 1 |  | claude | US-WNE-40-7 | [US-WNE-40](stories/US-WNE-40.md) |
| [US-WNE-40-2](tasks/US-WNE-40-2.md) | Test: Device A can communicate with Device B and Device C | ✅ done | — |  | — | — | [US-WNE-40](stories/US-WNE-40.md) |
| [US-WNE-40-3](tasks/US-WNE-40-3.md) | Test: Devices B and C can communicate with each other when configured as peers | ✅ done | — |  | — | — | [US-WNE-40](stories/US-WNE-40.md) |
| [US-WNE-40-4](tasks/US-WNE-40-4.md) | Test: Each peer relationship has independent handshakes | ✅ done | — |  | — | — | [US-WNE-40](stories/US-WNE-40.md) |
| [US-WNE-40-5](tasks/US-WNE-40-5.md) | Test: Test message routing between non-directly-connected peers if applicable via AllowedIPs | ✅ done | — |  | — | — | [US-WNE-40](stories/US-WNE-40.md) |
| [US-WNE-40-6](tasks/US-WNE-40-6.md) | Test: All peers can be created and torn down cleanly | ✅ done | — |  | — | — | [US-WNE-40](stories/US-WNE-40.md) |
| [US-WNE-40-7](tasks/US-WNE-40-7.md) | Implement WgMeshTopology test helper for multi-peer setup | ✅ done | 3 |  | claude | — | [US-WNE-40](stories/US-WNE-40.md) |
| [US-WNE-40-8](tasks/US-WNE-40-8.md) | Test: Three-peer mesh communication | ✅ done | 3 |  | claude | US-WNE-40-7 | [US-WNE-40](stories/US-WNE-40.md) |
| [US-WNE-40-9](tasks/US-WNE-40-9.md) | Test: Star topology with hub device | ✅ done | 2 |  | claude | US-WNE-40-7 | [US-WNE-40](stories/US-WNE-40.md) |
| [US-WNE-41-1](tasks/US-WNE-41-1.md) | Test: Configure peer with restricted AllowedIPs (e.g. only 10.0.0.1/32) | ✅ done | — |  | — | — | [US-WNE-41](stories/US-WNE-41.md) |
| [US-WNE-41-10](tasks/US-WNE-41-10.md) | Test: Various CIDR ranges (/32, /24, /16, /0) | ✅ done | 2 |  | claude | US-WNE-41-6 | [US-WNE-41](stories/US-WNE-41.md) |
| [US-WNE-41-2](tasks/US-WNE-41-2.md) | Test: Verify traffic to allowed IP succeeds | ✅ done | — |  | — | — | [US-WNE-41](stories/US-WNE-41.md) |
| [US-WNE-41-3](tasks/US-WNE-41-3.md) | Test: Verify traffic to disallowed IP is silently dropped (connection fails or times out) | ✅ done | — |  | — | — | [US-WNE-41](stories/US-WNE-41.md) |
| [US-WNE-41-4](tasks/US-WNE-41-4.md) | Test: Verify packets FROM wrong source IP are dropped | ✅ done | — |  | — | — | [US-WNE-41](stories/US-WNE-41.md) |
| [US-WNE-41-5](tasks/US-WNE-41-5.md) | Test: Test with various CIDR ranges (/32 and /24 and /16 and /0) | ✅ done | — |  | — | — | [US-WNE-41](stories/US-WNE-41.md) |
| [US-WNE-41-6](tasks/US-WNE-41-6.md) | Implement AllowedIPs test configuration helpers | ✅ done | 2 |  | claude | — | [US-WNE-41](stories/US-WNE-41.md) |
| [US-WNE-41-7](tasks/US-WNE-41-7.md) | Test: Traffic to allowed IP succeeds with /32 restriction | ✅ done | 1 |  | claude | US-WNE-41-6 | [US-WNE-41](stories/US-WNE-41.md) |
| [US-WNE-41-8](tasks/US-WNE-41-8.md) | Test: Traffic to disallowed IP is silently dropped | ✅ done | 2 |  | claude | US-WNE-41-6 | [US-WNE-41](stories/US-WNE-41.md) |
| [US-WNE-41-9](tasks/US-WNE-41-9.md) | Test: Packets from wrong source IP are dropped | ✅ done | 2 |  | claude | US-WNE-41-6 | [US-WNE-41](stories/US-WNE-41.md) |
| [US-WNE-42-1](tasks/US-WNE-42-1.md) | Test: WgSocket.sln at repo root with all projects referenced | ✅ done | 1 |  | claude | US-WNE-42-8 | [US-WNE-42](stories/US-WNE-42.md) |
| [US-WNE-42-10](tasks/US-WNE-42-10.md) | Configure src/wgsocket-native/Cargo.toml as cdylib | ✅ done | 1 |  | claude | — | [US-WNE-42](stories/US-WNE-42.md) |
| [US-WNE-42-11](tasks/US-WNE-42-11.md) | Configure local native library path for dev builds | ✅ done | 1 |  | claude | — | [US-WNE-42](stories/US-WNE-42.md) |
| [US-WNE-42-12](tasks/US-WNE-42-12.md) | Verify local build and test roundtrip | ✅ done | 1 |  | — | US-WNE-42-8, US-WNE-42-9, US-WNE-42-10, US-WNE-42-11 | [US-WNE-42](stories/US-WNE-42.md) |
| [US-WNE-42-2](tasks/US-WNE-42-2.md) | Test: src/WgSocket/WgSocket.csproj targeting net8.0 with proper SDK-style format | ✅ done | 1 |  | claude | US-WNE-42-8 | [US-WNE-42](stories/US-WNE-42.md) |
| [US-WNE-42-3](tasks/US-WNE-42-3.md) | Test: src/WgSocket.Tests/WgSocket.Tests.csproj with xUnit and Microsoft.NET.Test.Sdk references | ✅ done | 1 |  | claude | US-WNE-42-9 | [US-WNE-42](stories/US-WNE-42.md) |
| [US-WNE-42-4](tasks/US-WNE-42-4.md) | Test: src/wgsocket-native/Cargo.toml configured as cdylib crate type | ✅ done | 1 |  | claude | US-WNE-42-10 | [US-WNE-42](stories/US-WNE-42.md) |
| [US-WNE-42-5](tasks/US-WNE-42-5.md) | Test: dotnet build succeeds locally without errors | ✅ done | 1 |  | claude | US-WNE-42-12 | [US-WNE-42](stories/US-WNE-42.md) |
| [US-WNE-42-6](tasks/US-WNE-42-6.md) | Test: dotnet test runs and passes locally | ⚪ todo | 1 |  | claude | US-WNE-42-12 | [US-WNE-42](stories/US-WNE-42.md) |
| [US-WNE-42-7](tasks/US-WNE-42-7.md) | Test: Local dev references native library via local path convention | ✅ done | 1 |  | claude | US-WNE-42-11 | [US-WNE-42](stories/US-WNE-42.md) |
| [US-WNE-42-8](tasks/US-WNE-42-8.md) | Create WgSocket.sln and src/WgSocket/WgSocket.csproj | ✅ done | 1 |  | claude | — | [US-WNE-42](stories/US-WNE-42.md) |
| [US-WNE-42-9](tasks/US-WNE-42-9.md) | Create src/WgSocket.Tests/WgSocket.Tests.csproj with xUnit | ✅ done | 1 |  | claude | — | [US-WNE-42](stories/US-WNE-42.md) |
| [US-WNE-43-1](tasks/US-WNE-43-1.md) | Test: Verify initial Noise_IKpsk2 handshake completes successfully | ✅ done | — |  | — | — | [US-WNE-43](stories/US-WNE-43.md) |
| [US-WNE-43-10](tasks/US-WNE-43-10.md) | Test: Handshake with PSK (pre-shared key) | ✅ done | 2 |  | claude | US-WNE-43-7 | [US-WNE-43](stories/US-WNE-43.md) |
| [US-WNE-43-11](tasks/US-WNE-43-11.md) | Test: Handshake timeout with unreachable peer | ✅ done | 1 |  | claude | US-WNE-43-7 | [US-WNE-43](stories/US-WNE-43.md) |
| [US-WNE-43-2](tasks/US-WNE-43-2.md) | Test: Verify data flows after handshake | ✅ done | — |  | — | — | [US-WNE-43](stories/US-WNE-43.md) |
| [US-WNE-43-3](tasks/US-WNE-43-3.md) | Test: Verify rekey occurs (force by time or packet count) | ✅ done | — |  | — | — | [US-WNE-43](stories/US-WNE-43.md) |
| [US-WNE-43-4](tasks/US-WNE-43-4.md) | Test: Verify data continues to flow after rekey without interruption | ✅ done | — |  | — | — | [US-WNE-43](stories/US-WNE-43.md) |
| [US-WNE-43-5](tasks/US-WNE-43-5.md) | Test: Verify handshake with PSK (pre-shared key) works correctly | ✅ done | — |  | — | — | [US-WNE-43](stories/US-WNE-43.md) |
| [US-WNE-43-6](tasks/US-WNE-43-6.md) | Test: Test handshake timeout when peer is unreachable | ✅ done | — |  | — | — | [US-WNE-43](stories/US-WNE-43.md) |
| [US-WNE-43-7](tasks/US-WNE-43-7.md) | Implement handshake observation helpers | ✅ done | 2 |  | claude | — | [US-WNE-43](stories/US-WNE-43.md) |
| [US-WNE-43-8](tasks/US-WNE-43-8.md) | Test: Initial Noise_IKpsk2 handshake completes and data flows | ✅ done | 1 |  | claude | US-WNE-43-7 | [US-WNE-43](stories/US-WNE-43.md) |
| [US-WNE-43-9](tasks/US-WNE-43-9.md) | Test: Rekey occurs and data continues flowing | ✅ done | 3 |  | claude | US-WNE-43-7 | [US-WNE-43](stories/US-WNE-43.md) |
| [US-WNE-44-1](tasks/US-WNE-44-1.md) | Test: Test connection refused when no listener is active | ✅ done | — |  | — | — | [US-WNE-44](stories/US-WNE-44.md) |
| [US-WNE-44-10](tasks/US-WNE-44-10.md) | Test: Clean disconnect via FIN handshake | ✅ done | 1 |  | claude | US-WNE-44-8 | [US-WNE-44](stories/US-WNE-44.md) |
| [US-WNE-44-11](tasks/US-WNE-44-11.md) | Test: Abrupt disconnect during active transfer | ✅ done | 2 |  | claude | US-WNE-44-8 | [US-WNE-44](stories/US-WNE-44.md) |
| [US-WNE-44-12](tasks/US-WNE-44-12.md) | Test: Reconnect after disconnect and socket reuse | ✅ done | 2 |  | claude | US-WNE-44-8 | [US-WNE-44](stories/US-WNE-44.md) |
| [US-WNE-44-2](tasks/US-WNE-44-2.md) | Test: Test connection to non-existent peer | ✅ done | — |  | — | — | [US-WNE-44](stories/US-WNE-44.md) |
| [US-WNE-44-3](tasks/US-WNE-44-3.md) | Test: Test clean disconnect via FIN handshake | ✅ done | — |  | — | — | [US-WNE-44](stories/US-WNE-44.md) |
| [US-WNE-44-4](tasks/US-WNE-44-4.md) | Test: Test abrupt disconnect when device is disposed during active transfer | ✅ done | — |  | — | — | [US-WNE-44](stories/US-WNE-44.md) |
| [US-WNE-44-5](tasks/US-WNE-44-5.md) | Test: Test reconnect after disconnect | ✅ done | — |  | — | — | [US-WNE-44](stories/US-WNE-44.md) |
| [US-WNE-44-6](tasks/US-WNE-44-6.md) | Test: Test socket reuse after close | ✅ done | — |  | — | — | [US-WNE-44](stories/US-WNE-44.md) |
| [US-WNE-44-7](tasks/US-WNE-44-7.md) | Test: Test timeout on blocked receive | ✅ done | — |  | — | — | [US-WNE-44](stories/US-WNE-44.md) |
| [US-WNE-44-8](tasks/US-WNE-44-8.md) | Implement connection lifecycle test helpers | ✅ done | 2 |  | claude | — | [US-WNE-44](stories/US-WNE-44.md) |
| [US-WNE-44-9](tasks/US-WNE-44-9.md) | Test: Connection refused and non-existent peer | ✅ done | 2 |  | claude | US-WNE-44-8 | [US-WNE-44](stories/US-WNE-44.md) |
| [US-WNE-45-1](tasks/US-WNE-45-1.md) | Test: cargo build --release works for all 4 targets (x86_64-pc-windows-msvc x86_64-unknown-linux-gnu x86_64-apple-dar... | 🛑 blocked | 2 |  | claude | — | [US-WNE-45](stories/US-WNE-45.md) |
| [US-WNE-45-10](tasks/US-WNE-45-10.md) | Document cross-compilation prerequisites | ✅ done | 1 |  | claude | — | [US-WNE-45](stories/US-WNE-45.md) |
| [US-WNE-45-11](tasks/US-WNE-45-11.md) | Verify cross-compilation for host platform target | ✅ done | 1 |  | claude | US-WNE-45-7, US-WNE-45-8, US-WNE-45-9 | [US-WNE-45](stories/US-WNE-45.md) |
| [US-WNE-45-2](tasks/US-WNE-45-2.md) | Test: Cross-compilation toolchains and prerequisites documented in CONTRIBUTING.md or build docs | ✅ done | 2 |  | claude | — | [US-WNE-45](stories/US-WNE-45.md) |
| [US-WNE-45-3](tasks/US-WNE-45-3.md) | Test: Output binaries placed in correct runtimes/{rid}/native/ directories matching NuGet RID conventions | ✅ done | 2 |  | claude | — | [US-WNE-45](stories/US-WNE-45.md) |
| [US-WNE-45-4](tasks/US-WNE-45-4.md) | Test: Build script or Makefile automates multi-target build with a single command | ✅ done | 2 |  | claude | — | [US-WNE-45](stories/US-WNE-45.md) |
| [US-WNE-45-5](tasks/US-WNE-45-5.md) | Test: cargo fmt --check passes with no formatting violations | ✅ done | 1 |  | claude | — | [US-WNE-45](stories/US-WNE-45.md) |
| [US-WNE-45-6](tasks/US-WNE-45-6.md) | Test: cargo clippy -- -D warnings passes with no warnings | ✅ done | 1 |  | claude | — | [US-WNE-45](stories/US-WNE-45.md) |
| [US-WNE-45-7](tasks/US-WNE-45-7.md) | Create cross-compilation build script | ✅ done | 2 |  | claude | — | [US-WNE-45](stories/US-WNE-45.md) |
| [US-WNE-45-8](tasks/US-WNE-45-8.md) | Set up runtimes/{rid}/native/ output directory mapping | ✅ done | 1 |  | claude | US-WNE-45-7 | [US-WNE-45](stories/US-WNE-45.md) |
| [US-WNE-45-9](tasks/US-WNE-45-9.md) | Add cargo fmt and clippy configuration | ✅ done | 1 |  | claude | — | [US-WNE-45](stories/US-WNE-45.md) |
| [US-WNE-46-1](tasks/US-WNE-46-1.md) | Test: Test WgDeviceHandle creation and disposal | ✅ done | 2 |  | claude | — | [US-WNE-46](stories/US-WNE-46.md) |
| [US-WNE-46-10](tasks/US-WNE-46-10.md) | Implement double-dispose and post-dispose safety tests | ✅ done | 1 |  | claude | US-WNE-46-8 | [US-WNE-46](stories/US-WNE-46.md) |
| [US-WNE-46-11](tasks/US-WNE-46-11.md) | Implement disposal ordering and finalizer tests | ✅ done | 2 |  | claude | US-WNE-46-8 | [US-WNE-46](stories/US-WNE-46.md) |
| [US-WNE-46-2](tasks/US-WNE-46-2.md) | Test: Test WgSocketHandle creation and disposal | ✅ done | 2 |  | claude | — | [US-WNE-46](stories/US-WNE-46.md) |
| [US-WNE-46-3](tasks/US-WNE-46-3.md) | Test: Test double-dispose is safe (no exception and no crash) | ✅ done | 1 |  | claude | — | [US-WNE-46](stories/US-WNE-46.md) |
| [US-WNE-46-4](tasks/US-WNE-46-4.md) | Test: Test dispose order (socket before device) | ✅ done | 1 |  | claude | — | [US-WNE-46](stories/US-WNE-46.md) |
| [US-WNE-46-5](tasks/US-WNE-46-5.md) | Test: Test finalizer fires on GC if not disposed | ✅ done | 2 |  | claude | — | [US-WNE-46](stories/US-WNE-46.md) |
| [US-WNE-46-6](tasks/US-WNE-46-6.md) | Test: Test ObjectDisposedException after dispose | ✅ done | 2 |  | claude | — | [US-WNE-46](stories/US-WNE-46.md) |
| [US-WNE-46-7](tasks/US-WNE-46-7.md) | Test: Test concurrent dispose from multiple threads | ✅ done | 2 |  | claude | — | [US-WNE-46](stories/US-WNE-46.md) |
| [US-WNE-46-8](tasks/US-WNE-46-8.md) | Scaffold SafeHandle test infrastructure with mock release callbacks | ✅ done | 1 |  | claude | — | [US-WNE-46](stories/US-WNE-46.md) |
| [US-WNE-46-9](tasks/US-WNE-46-9.md) | Implement handle creation and single-dispose tests | ✅ done | 1 |  | claude | US-WNE-46-8 | [US-WNE-46](stories/US-WNE-46.md) |
| [US-WNE-47-1](tasks/US-WNE-47-1.md) | Test: Measure single-stream TCP throughput (bytes/sec) through tunnel | ✅ done | — |  | — | — | [US-WNE-47](stories/US-WNE-47.md) |
| [US-WNE-47-10](tasks/US-WNE-47-10.md) | Test: Throughput benchmarks produce valid results | ✅ done | 2 |  | claude | US-WNE-47-8, US-WNE-47-9 | [US-WNE-47](stories/US-WNE-47.md) |
| [US-WNE-47-11](tasks/US-WNE-47-11.md) | Implement CI benchmark result logging and comparison | ✅ done | 2 |  | claude | US-WNE-47-8 | [US-WNE-47](stories/US-WNE-47.md) |
| [US-WNE-47-2](tasks/US-WNE-47-2.md) | Test: Measure latency (roundtrip time for small packets) | ✅ done | — |  | — | — | [US-WNE-47](stories/US-WNE-47.md) |
| [US-WNE-47-3](tasks/US-WNE-47-3.md) | Test: Compare against baseline (direct socket with no tunnel) to quantify overhead | ✅ done | — |  | — | — | [US-WNE-47](stories/US-WNE-47.md) |
| [US-WNE-47-4](tasks/US-WNE-47-4.md) | Test: Test with different buffer sizes (4KB and 64KB and 256KB) | ✅ done | — |  | — | — | [US-WNE-47](stories/US-WNE-47.md) |
| [US-WNE-47-5](tasks/US-WNE-47-5.md) | Test: Test sustained transfer (100MB+) for stability | ✅ done | — |  | — | — | [US-WNE-47](stories/US-WNE-47.md) |
| [US-WNE-47-6](tasks/US-WNE-47-6.md) | Test: Results logged to console/file for CI tracking | ✅ done | — |  | — | — | [US-WNE-47](stories/US-WNE-47.md) |
| [US-WNE-47-7](tasks/US-WNE-47-7.md) | Test: BenchmarkDotNet or similar for reproducible results | ✅ done | — |  | — | — | [US-WNE-47](stories/US-WNE-47.md) |
| [US-WNE-47-8](tasks/US-WNE-47-8.md) | Implement BenchmarkDotNet benchmark harness for tunnel throughput | ✅ done | 3 |  | claude | — | [US-WNE-47](stories/US-WNE-47.md) |
| [US-WNE-47-9](tasks/US-WNE-47-9.md) | Implement sustained transfer stability benchmark | ✅ done | 2 |  | claude | — | [US-WNE-47](stories/US-WNE-47.md) |
| [US-WNE-48-1](tasks/US-WNE-48-1.md) | Test: Pipeline triggers on push to main and pull_request to main | ✅ done | 1 |  | claude | — | [US-WNE-48](stories/US-WNE-48.md) |
| [US-WNE-48-10](tasks/US-WNE-48-10.md) | Create dotnet-build CI job with artifact download | ✅ done | 2 |  | claude | US-WNE-48-9 | [US-WNE-48](stories/US-WNE-48.md) |
| [US-WNE-48-11](tasks/US-WNE-48-11.md) | Add dotnet pack step to CI | ✅ done | 1 |  | claude | US-WNE-48-10 | [US-WNE-48](stories/US-WNE-48.md) |
| [US-WNE-48-12](tasks/US-WNE-48-12.md) | Validate CI pipeline end-to-end | ✅ done | 2 |  | claude | US-WNE-48-7, US-WNE-48-8, US-WNE-48-9, US-WNE-48-10, US-WNE-48-11 | [US-WNE-48](stories/US-WNE-48.md) |
| [US-WNE-48-2](tasks/US-WNE-48-2.md) | Test: rust-build job uses a matrix strategy for 4 targets: windows-latest (win-x64) and ubuntu-latest (linux-x64) and... | ✅ done | 2 |  | claude | — | [US-WNE-48](stories/US-WNE-48.md) |
| [US-WNE-48-3](tasks/US-WNE-48-3.md) | Test: Each matrix leg runs cargo fmt --check and cargo clippy -- -D warnings and cargo test (native only) and cargo b... | ✅ done | 2 |  | claude | — | [US-WNE-48](stories/US-WNE-48.md) |
| [US-WNE-48-4](tasks/US-WNE-48-4.md) | Test: Native binaries uploaded as GitHub Actions artifacts per target | ✅ done | 2 |  | claude | — | [US-WNE-48](stories/US-WNE-48.md) |
| [US-WNE-48-5](tasks/US-WNE-48-5.md) | Test: dotnet-build job depends on rust-build: downloads all 4 artifacts and runs dotnet build and dotnet test and dot... | ✅ done | 2 |  | claude | — | [US-WNE-48](stories/US-WNE-48.md) |
| [US-WNE-48-6](tasks/US-WNE-48-6.md) | Test: Full pipeline completes in under 15 minutes | ✅ done | 2 |  | claude | — | [US-WNE-48](stories/US-WNE-48.md) |
| [US-WNE-48-7](tasks/US-WNE-48-7.md) | Create rust-build CI workflow with matrix strategy | ✅ done | 2 |  | claude | — | [US-WNE-48](stories/US-WNE-48.md) |
| [US-WNE-48-8](tasks/US-WNE-48-8.md) | Add Rust quality checks to each matrix leg | ✅ done | 1 |  | claude | US-WNE-48-7 | [US-WNE-48](stories/US-WNE-48.md) |
| [US-WNE-48-9](tasks/US-WNE-48-9.md) | Upload native binaries as CI artifacts | ✅ done | 1 |  | claude | US-WNE-48-7 | [US-WNE-48](stories/US-WNE-48.md) |
| [US-WNE-49-1](tasks/US-WNE-49-1.md) | Test: Test WgSocket connecting to wireguard-go peer if available in CI | ✅ done | — |  | — | — | [US-WNE-49](stories/US-WNE-49.md) |
| [US-WNE-49-10](tasks/US-WNE-49-10.md) | Test: wireguard-go connects to WgSocket listener | ✅ done | 3 |  | claude | US-WNE-49-7, US-WNE-49-8 | [US-WNE-49](stories/US-WNE-49.md) |
| [US-WNE-49-11](tasks/US-WNE-49-11.md) | Document external peer interop setup for local testing | ✅ done | 1 |  | claude | US-WNE-49-9, US-WNE-49-10 | [US-WNE-49](stories/US-WNE-49.md) |
| [US-WNE-49-2](tasks/US-WNE-49-2.md) | Test: Test wireguard-go connecting to WgSocket listener | ✅ done | — |  | — | — | [US-WNE-49](stories/US-WNE-49.md) |
| [US-WNE-49-3](tasks/US-WNE-49-3.md) | Test: Verify handshake interop between implementations | ✅ done | — |  | — | — | [US-WNE-49](stories/US-WNE-49.md) |
| [US-WNE-49-4](tasks/US-WNE-49-4.md) | Test: Verify data transfer between implementations | ✅ done | — |  | — | — | [US-WNE-49](stories/US-WNE-49.md) |
| [US-WNE-49-5](tasks/US-WNE-49-5.md) | Test: Skip gracefully if wireguard-go not available | ✅ done | — |  | — | — | [US-WNE-49](stories/US-WNE-49.md) |
| [US-WNE-49-6](tasks/US-WNE-49-6.md) | Test: Document how to set up the external peer for local testing | ✅ done | — |  | — | — | [US-WNE-49](stories/US-WNE-49.md) |
| [US-WNE-49-7](tasks/US-WNE-49-7.md) | Implement wireguard-go process manager for interop tests | ✅ done | 3 |  | claude | — | [US-WNE-49](stories/US-WNE-49.md) |
| [US-WNE-49-8](tasks/US-WNE-49-8.md) | Implement interop test configuration generator | ✅ done | 2 |  | claude | — | [US-WNE-49](stories/US-WNE-49.md) |
| [US-WNE-49-9](tasks/US-WNE-49-9.md) | Test: WgSocket connects to wireguard-go peer | ✅ done | 3 |  | claude | US-WNE-49-7, US-WNE-49-8 | [US-WNE-49](stories/US-WNE-49.md) |
| [US-WNE-5-1](tasks/US-WNE-5-1.md) | Test: Can create a boringtun Tunn instance from a private key and peer config | ✅ done | 2 |  | claude | — | [US-WNE-5](stories/US-WNE-5.md) |
| [US-WNE-5-2](tasks/US-WNE-5-2.md) | Test: Can encrypt plaintext IP packets into WireGuard transport messages | ✅ done | 2 |  | claude | — | [US-WNE-5](stories/US-WNE-5.md) |
| [US-WNE-5-3](tasks/US-WNE-5-3.md) | Test: Can decrypt incoming WireGuard packets to plaintext IP packets | ✅ done | 2 |  | claude | — | [US-WNE-5](stories/US-WNE-5.md) |
| [US-WNE-5-4](tasks/US-WNE-5-4.md) | Test: Handshake initiation and response work correctly | ✅ done | 2 |  | claude | — | [US-WNE-5](stories/US-WNE-5.md) |
| [US-WNE-5-5](tasks/US-WNE-5-5.md) | Test: Timer events (rekey and keepalive) are handled | ✅ done | 2 |  | claude | — | [US-WNE-5](stories/US-WNE-5.md) |
| [US-WNE-5-6](tasks/US-WNE-5-6.md) | Implement Tunn instance creation from private key and peer config | ✅ done | 2 |  | claude | — | [US-WNE-5](stories/US-WNE-5.md) |
| [US-WNE-5-7](tasks/US-WNE-5-7.md) | Implement encrypt and decrypt paths through boringtun | ✅ done | 2 |  | claude | — | [US-WNE-5](stories/US-WNE-5.md) |
| [US-WNE-5-8](tasks/US-WNE-5-8.md) | Implement handshake initiation and timer event handling | ✅ done | 2 |  | claude | — | [US-WNE-5](stories/US-WNE-5.md) |
| [US-WNE-5-9](tasks/US-WNE-5-9.md) | Test boringtun encrypt/decrypt roundtrip with two tunnel instances | ✅ done | 2 |  | claude | US-WNE-5-6, US-WNE-5-7, US-WNE-5-8 | [US-WNE-5](stories/US-WNE-5.md) |
| [US-WNE-50-1](tasks/US-WNE-50-1.md) | Test: .csproj configured with NuGet metadata: PackageId and Version and Description and Authors and License and Repos... | ✅ done | 1 |  | claude | — | [US-WNE-50](stories/US-WNE-50.md) |
| [US-WNE-50-10](tasks/US-WNE-50-10.md) | Validate NuGet package contents and consumer install | ✅ done | 2 |  | claude | US-WNE-50-7, US-WNE-50-8, US-WNE-50-9 | [US-WNE-50](stories/US-WNE-50.md) |
| [US-WNE-50-2](tasks/US-WNE-50-2.md) | Test: Native binaries included via runtimes/{rid}/native/ directory conventions with correct MSBuild Content items | ✅ done | 2 |  | claude | — | [US-WNE-50](stories/US-WNE-50.md) |
| [US-WNE-50-3](tasks/US-WNE-50-3.md) | Test: dotnet pack produces a self-contained .nupkg containing all 4 native binaries | ✅ done | 2 |  | claude | — | [US-WNE-50](stories/US-WNE-50.md) |
| [US-WNE-50-4](tasks/US-WNE-50-4.md) | Test: Package size is reasonable at approximately 8-16MB with 4 native binaries | ✅ done | 2 |  | claude | — | [US-WNE-50](stories/US-WNE-50.md) |
| [US-WNE-50-5](tasks/US-WNE-50-5.md) | Test: Package installs correctly in a fresh .NET 8 console project | ✅ done | 2 |  | claude | — | [US-WNE-50](stories/US-WNE-50.md) |
| [US-WNE-50-6](tasks/US-WNE-50-6.md) | Test: Consumer project can resolve and P/Invoke load the native library after install without manual steps | ✅ done | 2 |  | claude | — | [US-WNE-50](stories/US-WNE-50.md) |
| [US-WNE-50-7](tasks/US-WNE-50-7.md) | Configure NuGet metadata in WgSocket.csproj | ✅ done | 1 |  | claude | — | [US-WNE-50](stories/US-WNE-50.md) |
| [US-WNE-50-8](tasks/US-WNE-50-8.md) | Configure runtimes/{rid}/native/ MSBuild items | ✅ done | 2 |  | claude | — | [US-WNE-50](stories/US-WNE-50.md) |
| [US-WNE-50-9](tasks/US-WNE-50-9.md) | Add .NET runtime native library resolution | ✅ done | 1 |  | claude | US-WNE-50-8 | [US-WNE-50](stories/US-WNE-50.md) |
| [US-WNE-51-1](tasks/US-WNE-51-1.md) | Test: Rust side uses zeroize crate on all key fields (private key and PSK and session keys) | ✅ done | 2 |  | claude | — | [US-WNE-51](stories/US-WNE-51.md) |
| [US-WNE-51-10](tasks/US-WNE-51-10.md) | Test: verify C# key buffer zeroing after Dispose | ✅ done | 1 |  | claude | US-WNE-51-7 | [US-WNE-51](stories/US-WNE-51.md) |
| [US-WNE-51-11](tasks/US-WNE-51-11.md) | Test: Debug/Display output never contains key material | ✅ done | 1 |  | claude | US-WNE-51-8 | [US-WNE-51](stories/US-WNE-51.md) |
| [US-WNE-51-2](tasks/US-WNE-51-2.md) | Test: Key material zeroed when WgDevice is dropped | ✅ done | 2 |  | claude | — | [US-WNE-51](stories/US-WNE-51.md) |
| [US-WNE-51-3](tasks/US-WNE-51-3.md) | Test: C# side uses fixed/pinned buffers and explicit zeroing for key parameters | ✅ done | 2 |  | claude | — | [US-WNE-51](stories/US-WNE-51.md) |
| [US-WNE-51-4](tasks/US-WNE-51-4.md) | Test: Verify with test: dump memory region after dispose and confirm keys are zeroed | ✅ done | 2 |  | claude | — | [US-WNE-51](stories/US-WNE-51.md) |
| [US-WNE-51-5](tasks/US-WNE-51-5.md) | Test: Debug output (Display/Debug traits) never includes key material | ✅ done | 2 |  | claude | — | [US-WNE-51](stories/US-WNE-51.md) |
| [US-WNE-51-6](tasks/US-WNE-51-6.md) | Add zeroize crate and derive Zeroize/ZeroizeOnDrop on all Rust key structs | ✅ done | 2 |  | claude | — | [US-WNE-51](stories/US-WNE-51.md) |
| [US-WNE-51-7](tasks/US-WNE-51-7.md) | Implement secure key handling on C# side with fixed/pinned buffers | ✅ done | 2 |  | — | US-WNE-51-6 | [US-WNE-51](stories/US-WNE-51.md) |
| [US-WNE-51-8](tasks/US-WNE-51-8.md) | Redact key material from Debug/Display trait implementations | ✅ done | 1 |  | claude | US-WNE-51-6 | [US-WNE-51](stories/US-WNE-51.md) |
| [US-WNE-51-9](tasks/US-WNE-51-9.md) | Test: verify memory zeroization after Rust WgDevice drop | ✅ done | 1 |  | claude | US-WNE-51-6 | [US-WNE-51](stories/US-WNE-51.md) |
| [US-WNE-52-1](tasks/US-WNE-52-1.md) | Test: CI step generates wgsocket.h via cbindgen from Rust source | ⚪ todo | — |  | — | — | [US-WNE-52](stories/US-WNE-52.md) |
| [US-WNE-52-2](tasks/US-WNE-52-2.md) | Test: Generated header is diffed against the checked-in header file | ⚪ todo | — |  | — | — | [US-WNE-52](stories/US-WNE-52.md) |
| [US-WNE-52-3](tasks/US-WNE-52-3.md) | Test: Build fails with a non-zero exit code if the header is stale (Rust exports changed but header not regenerated) | ⚪ todo | — |  | — | — | [US-WNE-52](stories/US-WNE-52.md) |
| [US-WNE-52-4](tasks/US-WNE-52-4.md) | Test: Error message clearly explains how to regenerate the header locally | ⚪ todo | — |  | — | — | [US-WNE-52](stories/US-WNE-52.md) |
| [US-WNE-52-5](tasks/US-WNE-52-5.md) | Test: cbindgen.toml configuration checked in and maintained | ⚪ todo | — |  | — | — | [US-WNE-52](stories/US-WNE-52.md) |
| [US-WNE-52-6](tasks/US-WNE-52-6.md) | Create cbindgen.toml and generate baseline header | ⚪ todo | 1 |  | — | — | [US-WNE-52](stories/US-WNE-52.md) |
| [US-WNE-52-7](tasks/US-WNE-52-7.md) | Add header staleness check script | ⚪ todo | 1 |  | — | — | [US-WNE-52](stories/US-WNE-52.md) |
| [US-WNE-52-8](tasks/US-WNE-52-8.md) | Integrate cbindgen check into CI workflow | ⚪ todo | 1 |  | — | — | [US-WNE-52](stories/US-WNE-52.md) |
| [US-WNE-52-9](tasks/US-WNE-52-9.md) | Verify staleness detection catches a real change | ⚪ todo | 1 |  | — | US-WNE-52-6, US-WNE-52-7, US-WNE-52-8 | [US-WNE-52](stories/US-WNE-52.md) |
| [US-WNE-53-1](tasks/US-WNE-53-1.md) | Test: Workflow triggers on manual dispatch (workflow_dispatch) or git tag matching v* pattern | ✅ done | 1 |  | claude | US-WNE-53-7 | [US-WNE-53](stories/US-WNE-53.md) |
| [US-WNE-53-10](tasks/US-WNE-53-10.md) | Validate publish workflow with dry run | ✅ done | 1 |  | claude | US-WNE-53-7, US-WNE-53-8, US-WNE-53-9 | [US-WNE-53](stories/US-WNE-53.md) |
| [US-WNE-53-2](tasks/US-WNE-53-2.md) | Test: Builds fresh from source (not from cached artifacts) to ensure reproducibility | ✅ done | 1 |  | claude | US-WNE-53-7 | [US-WNE-53](stories/US-WNE-53.md) |
| [US-WNE-53-3](tasks/US-WNE-53-3.md) | Test: Pushes .nupkg to nuget.org using NUGET_API_KEY secret | ✅ done | 1 |  | claude | US-WNE-53-9 | [US-WNE-53](stories/US-WNE-53.md) |
| [US-WNE-53-4](tasks/US-WNE-53-4.md) | Test: Version in .csproj matches Cargo.toml version (single source of truth) | ✅ done | 1 |  | claude | US-WNE-53-8 | [US-WNE-53](stories/US-WNE-53.md) |
| [US-WNE-53-5](tasks/US-WNE-53-5.md) | Test: GitHub release created automatically with tag name and changelog | ✅ done | 1 |  | claude | US-WNE-53-9 | [US-WNE-53](stories/US-WNE-53.md) |
| [US-WNE-53-6](tasks/US-WNE-53-6.md) | Test: Release includes the .nupkg as a downloadable asset | ✅ done | 1 |  | claude | US-WNE-53-9 | [US-WNE-53](stories/US-WNE-53.md) |
| [US-WNE-53-7](tasks/US-WNE-53-7.md) | Create publish workflow YAML | ✅ done | 2 |  | claude | — | [US-WNE-53](stories/US-WNE-53.md) |
| [US-WNE-53-8](tasks/US-WNE-53-8.md) | Add version synchronization between .csproj and Cargo.toml | ✅ done | 1 |  | claude | — | [US-WNE-53](stories/US-WNE-53.md) |
| [US-WNE-53-9](tasks/US-WNE-53-9.md) | Add NuGet push and GitHub release steps | ✅ done | 1 |  | claude | — | [US-WNE-53](stories/US-WNE-53.md) |
| [US-WNE-54-1](tasks/US-WNE-54-1.md) | Test: Test each error code maps to correct exception type | ✅ done | 1 |  | claude | — | [US-WNE-54](stories/US-WNE-54.md) |
| [US-WNE-54-2](tasks/US-WNE-54-2.md) | Test: Test exception message includes native error detail | ✅ done | 1 |  | claude | — | [US-WNE-54](stories/US-WNE-54.md) |
| [US-WNE-54-3](tasks/US-WNE-54-3.md) | Test: Test WgException.ErrorCode property | ✅ done | 1 |  | claude | — | [US-WNE-54](stories/US-WNE-54.md) |
| [US-WNE-54-4](tasks/US-WNE-54-4.md) | Test: Test throwing and catching specific exception types | ✅ done | 1 |  | claude | — | [US-WNE-54](stories/US-WNE-54.md) |
| [US-WNE-54-5](tasks/US-WNE-54-5.md) | Test: Test error codes not in enum produce generic WgException | ✅ done | 1 |  | claude | — | [US-WNE-54](stories/US-WNE-54.md) |
| [US-WNE-54-6](tasks/US-WNE-54-6.md) | Scaffold ExceptionMappingTests with error code table | ✅ done | 1 |  | claude | — | [US-WNE-54](stories/US-WNE-54.md) |
| [US-WNE-54-7](tasks/US-WNE-54-7.md) | Implement error code to exception type mapping tests | ✅ done | 2 |  | claude | US-WNE-54-6 | [US-WNE-54](stories/US-WNE-54.md) |
| [US-WNE-55-1](tasks/US-WNE-55-1.md) | Test: Console app in samples/EchoServer/ with its own .csproj referencing WgSocket | ✅ done | 1 |  | claude | US-WNE-55-9 | [US-WNE-55](stories/US-WNE-55.md) |
| [US-WNE-55-10](tasks/US-WNE-55-10.md) | Implement WgDevice setup and echo loop logic | ✅ done | 2 |  | claude | US-WNE-55-9 | [US-WNE-55](stories/US-WNE-55.md) |
| [US-WNE-55-11](tasks/US-WNE-55-11.md) | Create test wg.conf and sample README | ✅ done | 1 |  | claude | US-WNE-55-10 | [US-WNE-55](stories/US-WNE-55.md) |
| [US-WNE-55-2](tasks/US-WNE-55-2.md) | Test: Demonstrates WgDevice setup and configuration from wg.conf | ✅ done | 1 |  | claude | US-WNE-55-10 | [US-WNE-55](stories/US-WNE-55.md) |
| [US-WNE-55-3](tasks/US-WNE-55-3.md) | Test: Uses Socket.Listen and Accept to handle incoming connections | ✅ done | 1 |  | claude | US-WNE-55-10 | [US-WNE-55](stories/US-WNE-55.md) |
| [US-WNE-55-4](tasks/US-WNE-55-4.md) | Test: Implements a full echo loop that reads data and writes it back | ✅ done | 1 |  | claude | US-WNE-55-10 | [US-WNE-55](stories/US-WNE-55.md) |
| [US-WNE-55-5](tasks/US-WNE-55-5.md) | Test: Includes a wg.conf with test configuration and key pair for local testing | ✅ done | 1 |  | claude | US-WNE-55-9 | [US-WNE-55](stories/US-WNE-55.md) |
| [US-WNE-55-6](tasks/US-WNE-55-6.md) | Test: Runs against the ChatClient sample or any other WgSocket peer | ✅ done | 1 |  | claude | US-WNE-55-10 | [US-WNE-55](stories/US-WNE-55.md) |
| [US-WNE-55-7](tasks/US-WNE-55-7.md) | Test: Includes README.md with usage instructions and expected output | ✅ done | 1 |  | claude | US-WNE-55-10 | [US-WNE-55](stories/US-WNE-55.md) |
| [US-WNE-55-8](tasks/US-WNE-55-8.md) | Test: Shows the single-file import experience prominently with 'using WgSocket' as the only namespace change | ✅ done | 1 |  | claude | US-WNE-55-10 | [US-WNE-55](stories/US-WNE-55.md) |
| [US-WNE-55-9](tasks/US-WNE-55-9.md) | Scaffold EchoServer console app project | ✅ done | 1 |  | claude | — | [US-WNE-55](stories/US-WNE-55.md) |
| [US-WNE-56-1](tasks/US-WNE-56-1.md) | Test: Console app in samples/ChatClient/ with its own .csproj referencing WgSocket | ⚪ todo | — |  | — | — | [US-WNE-56](stories/US-WNE-56.md) |
| [US-WNE-56-10](tasks/US-WNE-56-10.md) | Implement async chat logic with bidirectional messaging | ⚪ todo | 2 |  | — | US-WNE-56-9 | [US-WNE-56](stories/US-WNE-56.md) |
| [US-WNE-56-11](tasks/US-WNE-56-11.md) | Create test wg.conf and sample README for ChatClient | ⚪ todo | 1 |  | — | US-WNE-56-10 | [US-WNE-56](stories/US-WNE-56.md) |
| [US-WNE-56-2](tasks/US-WNE-56-2.md) | Test: Demonstrates WgDevice setup and configuration from wg.conf | ⚪ todo | — |  | — | — | [US-WNE-56](stories/US-WNE-56.md) |
| [US-WNE-56-3](tasks/US-WNE-56-3.md) | Test: Uses Socket.Connect to establish outbound connection to a peer | ⚪ todo | — |  | — | — | [US-WNE-56](stories/US-WNE-56.md) |
| [US-WNE-56-4](tasks/US-WNE-56-4.md) | Test: Interactive send/receive loop with console input and output | ⚪ todo | — |  | — | — | [US-WNE-56](stories/US-WNE-56.md) |
| [US-WNE-56-5](tasks/US-WNE-56-5.md) | Test: Bidirectional messaging over WireGuard tunnel | ⚪ todo | — |  | — | — | [US-WNE-56](stories/US-WNE-56.md) |
| [US-WNE-56-6](tasks/US-WNE-56-6.md) | Test: Uses async API (ReadAsync/WriteAsync via NetworkStream) for non-blocking I/O | ⚪ todo | — |  | — | — | [US-WNE-56](stories/US-WNE-56.md) |
| [US-WNE-56-7](tasks/US-WNE-56-7.md) | Test: Includes wg.conf with test configuration and key pair for local testing | ⚪ todo | — |  | — | — | [US-WNE-56](stories/US-WNE-56.md) |
| [US-WNE-56-8](tasks/US-WNE-56-8.md) | Test: Includes README.md with usage instructions and expected output | ⚪ todo | — |  | — | — | [US-WNE-56](stories/US-WNE-56.md) |
| [US-WNE-56-9](tasks/US-WNE-56-9.md) | Scaffold ChatClient console app project | ⚪ todo | 1 |  | — | — | [US-WNE-56](stories/US-WNE-56.md) |
| [US-WNE-57-1](tasks/US-WNE-57-1.md) | Test: Project overview clearly states the value proposition: single-file import WireGuard networking | ✅ done | 1 |  | claude | — | [US-WNE-57](stories/US-WNE-57.md) |
| [US-WNE-57-2](tasks/US-WNE-57-2.md) | Test: Badge section with CI status and NuGet version and license | ✅ done | 1 |  | claude | US-WNE-57-8 | [US-WNE-57](stories/US-WNE-57.md) |
| [US-WNE-57-3](tasks/US-WNE-57-3.md) | Test: Quick-start section: install via NuGet and configure wg.conf and one-line type change example | ✅ done | 1 |  | claude | — | [US-WNE-57](stories/US-WNE-57.md) |
| [US-WNE-57-4](tasks/US-WNE-57-4.md) | Test: Code examples for common scenarios including echo server and client and NetworkStream usage | ✅ done | 1 |  | claude | US-WNE-57-9 | [US-WNE-57](stories/US-WNE-57.md) |
| [US-WNE-57-5](tasks/US-WNE-57-5.md) | Test: API overview table listing key types and their purposes | ✅ done | 1 |  | — | US-WNE-57-9 | [US-WNE-57](stories/US-WNE-57.md) |
| [US-WNE-57-6](tasks/US-WNE-57-6.md) | Test: Links to samples directory and architecture docs and contributing guide | ✅ done | 1 |  | claude | US-WNE-57-9 | [US-WNE-57](stories/US-WNE-57.md) |
| [US-WNE-57-7](tasks/US-WNE-57-7.md) | Test: Before-and-after code comparison showing the System.Net.Sockets to WgSocket type swap | ✅ done | 1 |  | claude | — | [US-WNE-57](stories/US-WNE-57.md) |
| [US-WNE-57-8](tasks/US-WNE-57-8.md) | Write README header, badges, and value proposition | ✅ done | 1 |  | claude | — | [US-WNE-57](stories/US-WNE-57.md) |
| [US-WNE-57-9](tasks/US-WNE-57-9.md) | Write quick-start guide and code examples | ✅ done | 1 |  | claude | US-WNE-57-8 | [US-WNE-57](stories/US-WNE-57.md) |
| [US-WNE-58-1](tasks/US-WNE-58-1.md) | Test: All public types have summary XML docs describing their purpose | ⚪ todo | — |  | — | — | [US-WNE-58](stories/US-WNE-58.md) |
| [US-WNE-58-2](tasks/US-WNE-58-2.md) | Test: All public methods have summary and param and returns and exception XML docs | ⚪ todo | — |  | — | — | [US-WNE-58](stories/US-WNE-58.md) |
| [US-WNE-58-3](tasks/US-WNE-58-3.md) | Test: All public properties have summary XML docs | ⚪ todo | — |  | — | — | [US-WNE-58](stories/US-WNE-58.md) |
| [US-WNE-58-4](tasks/US-WNE-58-4.md) | Test: WgSocket.csproj configured with GenerateDocumentationFile=true to produce XML doc file | ⚪ todo | — |  | — | — | [US-WNE-58](stories/US-WNE-58.md) |
| [US-WNE-58-5](tasks/US-WNE-58-5.md) | Test: No CS1591 compiler warnings for missing XML docs on public members | ⚪ todo | — |  | — | — | [US-WNE-58](stories/US-WNE-58.md) |
| [US-WNE-58-6](tasks/US-WNE-58-6.md) | Test: IntelliSense shows helpful descriptions when consuming the library in other projects | ⚪ todo | — |  | — | — | [US-WNE-58](stories/US-WNE-58.md) |
| [US-WNE-58-7](tasks/US-WNE-58-7.md) | Configure .csproj for XML documentation generation | ⚪ todo | 1 |  | — | — | [US-WNE-58](stories/US-WNE-58.md) |
| [US-WNE-58-8](tasks/US-WNE-58-8.md) | Add XML doc comments to Socket and NetworkStream types | ⚪ todo | 2 |  | — | US-WNE-58-7 | [US-WNE-58](stories/US-WNE-58.md) |
| [US-WNE-58-9](tasks/US-WNE-58-9.md) | Add XML doc comments to WgDevice, WgConfig, and WgPeer types | ⚪ todo | 2 |  | — | US-WNE-58-7 | [US-WNE-58](stories/US-WNE-58.md) |
| [US-WNE-59-1](tasks/US-WNE-59-1.md) | Test: Private key and PSK fields never appear in log output at any level (Trace through Critical) | ✅ done | 1 |  | claude | — | [US-WNE-59](stories/US-WNE-59.md) |
| [US-WNE-59-2](tasks/US-WNE-59-2.md) | Test: Test: enable all log levels and perform full lifecycle and grep logs for key material — must find nothing | ✅ done | 1 |  | claude | — | [US-WNE-59](stories/US-WNE-59.md) |
| [US-WNE-59-3](tasks/US-WNE-59-3.md) | Test: Structured logging fields for keys are redacted | ✅ done | 1 |  | claude | — | [US-WNE-59](stories/US-WNE-59.md) |
| [US-WNE-59-4](tasks/US-WNE-59-4.md) | Test: Code review checklist item for no-log enforcement documented | ✅ done | 1 |  | claude | — | [US-WNE-59](stories/US-WNE-59.md) |
| [US-WNE-59-5](tasks/US-WNE-59-5.md) | Audit and redact all Rust log statements touching key material | ✅ done | 2 |  | claude | — | [US-WNE-59](stories/US-WNE-59.md) |
| [US-WNE-59-6](tasks/US-WNE-59-6.md) | Audit and redact all C# log statements touching key material | ✅ done | 1 |  | claude | US-WNE-59-5 | [US-WNE-59](stories/US-WNE-59.md) |
| [US-WNE-59-7](tasks/US-WNE-59-7.md) | Test: full lifecycle log capture confirms no key material leakage | ✅ done | 2 |  | claude | US-WNE-59-5, US-WNE-59-6 | [US-WNE-59](stories/US-WNE-59.md) |
| [US-WNE-6-1](tasks/US-WNE-6-1.md) | Test: Builder pattern with fluent API (ConfigBuilder::new().private_key(...).peer(...).build()) | ✅ done | 1 |  | claude | US-WNE-6-5, US-WNE-6-6 | [US-WNE-6](stories/US-WNE-6.md) |
| [US-WNE-6-2](tasks/US-WNE-6-2.md) | Test: Accepts raw byte slices for keys (not just base64 strings) | ✅ done | 1 |  | claude | US-WNE-6-5 | [US-WNE-6](stories/US-WNE-6.md) |
| [US-WNE-6-3](tasks/US-WNE-6-3.md) | Test: Validates on build() call reusing the config validation logic | ✅ done | 1 |  | claude | US-WNE-6-6 | [US-WNE-6](stories/US-WNE-6.md) |
| [US-WNE-6-4](tasks/US-WNE-6-4.md) | Test: Can construct config equivalent to any valid wg.conf file | ✅ done | 1 |  | claude | US-WNE-6-6 | [US-WNE-6](stories/US-WNE-6.md) |
| [US-WNE-6-5](tasks/US-WNE-6-5.md) | Implement ConfigBuilder struct | ✅ done | 1 |  | claude | — | [US-WNE-6](stories/US-WNE-6.md) |
| [US-WNE-6-6](tasks/US-WNE-6-6.md) | Implement PeerBuilder and build() finalization | ✅ done | 2 |  | claude | US-WNE-6-5 | [US-WNE-6](stories/US-WNE-6.md) |
| [US-WNE-6-7](tasks/US-WNE-6-7.md) | Tests for config builder | ✅ done | 2 |  | claude | US-WNE-6-5, US-WNE-6-6 | [US-WNE-6](stories/US-WNE-6.md) |
| [US-WNE-60-1](tasks/US-WNE-60-1.md) | Test: Test Socket constructor creates valid instance | ✅ done | 1 |  | claude | — | [US-WNE-60](stories/US-WNE-60.md) |
| [US-WNE-60-10](tasks/US-WNE-60-10.md) | Scaffold WgSocketTests with mock native backend | ✅ done | 1 |  | claude | — | [US-WNE-60](stories/US-WNE-60.md) |
| [US-WNE-60-11](tasks/US-WNE-60-11.md) | Implement constructor and connection method signature tests | ✅ done | 1 |  | claude | US-WNE-60-10 | [US-WNE-60](stories/US-WNE-60.md) |
| [US-WNE-60-12](tasks/US-WNE-60-12.md) | Implement server-side and data transfer method signature tests | ✅ done | 2 |  | claude | US-WNE-60-10 | [US-WNE-60](stories/US-WNE-60.md) |
| [US-WNE-60-13](tasks/US-WNE-60-13.md) | Implement property accessor and state validation tests | ✅ done | 2 |  | claude | US-WNE-60-11 | [US-WNE-60](stories/US-WNE-60.md) |
| [US-WNE-60-14](tasks/US-WNE-60-14.md) | Implement disposal and CancellationToken tests | ✅ done | 2 |  | claude | US-WNE-60-12 | [US-WNE-60](stories/US-WNE-60.md) |
| [US-WNE-60-2](tasks/US-WNE-60-2.md) | Test: Test Connect/ConnectAsync method signatures match expected | ✅ done | 1 |  | claude | — | [US-WNE-60](stories/US-WNE-60.md) |
| [US-WNE-60-3](tasks/US-WNE-60-3.md) | Test: Test Bind/Listen/Accept/AcceptAsync signatures | ✅ done | 1 |  | claude | — | [US-WNE-60](stories/US-WNE-60.md) |
| [US-WNE-60-4](tasks/US-WNE-60-4.md) | Test: Test Send/SendAsync/Receive/ReceiveAsync signatures | ✅ done | 1 |  | claude | — | [US-WNE-60](stories/US-WNE-60.md) |
| [US-WNE-60-5](tasks/US-WNE-60-5.md) | Test: Test Close/Dispose releases resources | ✅ done | 1 |  | claude | — | [US-WNE-60](stories/US-WNE-60.md) |
| [US-WNE-60-6](tasks/US-WNE-60-6.md) | Test: Test property accessors (Connected and LocalEndPoint and RemoteEndPoint and Available) | ✅ done | 1 |  | claude | — | [US-WNE-60](stories/US-WNE-60.md) |
| [US-WNE-60-7](tasks/US-WNE-60-7.md) | Test: Test state validation (Send before Connect throws) | ✅ done | 1 |  | claude | — | [US-WNE-60](stories/US-WNE-60.md) |
| [US-WNE-60-8](tasks/US-WNE-60-8.md) | Test: Test Blocking property toggle | ✅ done | 1 |  | claude | — | [US-WNE-60](stories/US-WNE-60.md) |
| [US-WNE-60-9](tasks/US-WNE-60-9.md) | Test: Test CancellationToken support in async methods | ✅ done | 1 |  | claude | — | [US-WNE-60](stories/US-WNE-60.md) |
| [US-WNE-61-1](tasks/US-WNE-61-1.md) | Test: Generated API reference from XML docs using docfx or similar tool | ⚪ todo | — |  | — | — | [US-WNE-61](stories/US-WNE-61.md) |
| [US-WNE-61-2](tasks/US-WNE-61-2.md) | Test: Hosted on GitHub Pages or included as static HTML in the repo | ⚪ todo | — |  | — | — | [US-WNE-61](stories/US-WNE-61.md) |
| [US-WNE-61-3](tasks/US-WNE-61-3.md) | Test: Covers all public types: Socket and WgDevice and WgConfig and WgPeer and NetworkStream | ⚪ todo | — |  | — | — | [US-WNE-61](stories/US-WNE-61.md) |
| [US-WNE-61-4](tasks/US-WNE-61-4.md) | Test: Includes code examples in doc comments that render in the reference | ⚪ todo | — |  | — | — | [US-WNE-61](stories/US-WNE-61.md) |
| [US-WNE-61-5](tasks/US-WNE-61-5.md) | Test: Cross-references between related types with clickable links | ⚪ todo | — |  | — | — | [US-WNE-61](stories/US-WNE-61.md) |
| [US-WNE-61-6](tasks/US-WNE-61-6.md) | Test: Build step in CI to regenerate docs on release | ⚪ todo | — |  | — | — | [US-WNE-61](stories/US-WNE-61.md) |
| [US-WNE-61-7](tasks/US-WNE-61-7.md) | Set up docfx project and configuration | ⚪ todo | 2 |  | — | — | [US-WNE-61](stories/US-WNE-61.md) |
| [US-WNE-61-8](tasks/US-WNE-61-8.md) | Add code examples to doc comments for API reference | ⚪ todo | 1 |  | — | US-WNE-61-7 | [US-WNE-61](stories/US-WNE-61.md) |
| [US-WNE-61-9](tasks/US-WNE-61-9.md) | Add GitHub Pages deployment and CI doc generation | ⚪ todo | 2 |  | — | US-WNE-61-7 | [US-WNE-61](stories/US-WNE-61.md) |
| [US-WNE-62-1](tasks/US-WNE-62-1.md) | Test: cargo-fuzz harness targeting all extern C functions | ⚪ todo | — |  | — | — | [US-WNE-62](stories/US-WNE-62.md) |
| [US-WNE-62-10](tasks/US-WNE-62-10.md) | Implement fuzz target for wg_send and wg_recv with arbitrary buffers | ⚪ todo | 2 |  | — | — | [US-WNE-62](stories/US-WNE-62.md) |
| [US-WNE-62-11](tasks/US-WNE-62-11.md) | Implement fuzz target for wg_connect with arbitrary addresses | ⚪ todo | 1 |  | — | — | [US-WNE-62](stories/US-WNE-62.md) |
| [US-WNE-62-12](tasks/US-WNE-62-12.md) | Implement fuzz target for handle validation with random usize values | ⚪ todo | 2 |  | — | — | [US-WNE-62](stories/US-WNE-62.md) |
| [US-WNE-62-13](tasks/US-WNE-62-13.md) | Add CI workflow for nightly/on-demand fuzz runs | ⚪ todo | 1 |  | — | — | [US-WNE-62](stories/US-WNE-62.md) |
| [US-WNE-62-14](tasks/US-WNE-62-14.md) | Test: verify fuzz corpus seeds produce no panics or UB | ⚪ todo | 2 |  | — | US-WNE-62-8, US-WNE-62-9, US-WNE-62-10, US-WNE-62-11, US-WNE-62-12 | [US-WNE-62](stories/US-WNE-62.md) |
| [US-WNE-62-2](tasks/US-WNE-62-2.md) | Test: Fuzz wg_device_new with arbitrary config strings | ⚪ todo | — |  | — | — | [US-WNE-62](stories/US-WNE-62.md) |
| [US-WNE-62-3](tasks/US-WNE-62-3.md) | Test: Fuzz wg_send/wg_recv with arbitrary buffer sizes and contents | ⚪ todo | — |  | — | — | [US-WNE-62](stories/US-WNE-62.md) |
| [US-WNE-62-4](tasks/US-WNE-62-4.md) | Test: Fuzz wg_connect with arbitrary address/port combinations | ⚪ todo | — |  | — | — | [US-WNE-62](stories/US-WNE-62.md) |
| [US-WNE-62-5](tasks/US-WNE-62-5.md) | Test: Fuzz handle values (random usize) | ⚪ todo | — |  | — | — | [US-WNE-62](stories/US-WNE-62.md) |
| [US-WNE-62-6](tasks/US-WNE-62-6.md) | Test: No panics and no segfaults and no undefined behavior under fuzz | ⚪ todo | — |  | — | — | [US-WNE-62](stories/US-WNE-62.md) |
| [US-WNE-62-7](tasks/US-WNE-62-7.md) | Test: CI integration (nightly or on-demand) | ⚪ todo | — |  | — | — | [US-WNE-62](stories/US-WNE-62.md) |
| [US-WNE-62-8](tasks/US-WNE-62-8.md) | Set up cargo-fuzz project structure and base harness | ⚪ todo | 2 |  | — | — | [US-WNE-62](stories/US-WNE-62.md) |
| [US-WNE-62-9](tasks/US-WNE-62-9.md) | Implement fuzz target for wg_device_new with arbitrary configs | ⚪ todo | 2 |  | — | — | [US-WNE-62](stories/US-WNE-62.md) |
| [US-WNE-63-1](tasks/US-WNE-63-1.md) | Test: Test NetworkStream wraps Socket correctly | ⚪ todo | — |  | — | — | [US-WNE-63](stories/US-WNE-63.md) |
| [US-WNE-63-10](tasks/US-WNE-63-10.md) | Implement disposal behavior and StreamReader/StreamWriter integration tests | ⚪ todo | 1 |  | — | US-WNE-63-8 | [US-WNE-63](stories/US-WNE-63.md) |
| [US-WNE-63-2](tasks/US-WNE-63-2.md) | Test: Test Read delegates to Socket.Receive | ⚪ todo | — |  | — | — | [US-WNE-63](stories/US-WNE-63.md) |
| [US-WNE-63-3](tasks/US-WNE-63-3.md) | Test: Test Write delegates to Socket.Send | ⚪ todo | — |  | — | — | [US-WNE-63](stories/US-WNE-63.md) |
| [US-WNE-63-4](tasks/US-WNE-63-4.md) | Test: Test ReadAsync/WriteAsync delegate to async socket methods | ⚪ todo | — |  | — | — | [US-WNE-63](stories/US-WNE-63.md) |
| [US-WNE-63-5](tasks/US-WNE-63-5.md) | Test: Test CanRead/CanWrite/CanSeek values | ⚪ todo | — |  | — | — | [US-WNE-63](stories/US-WNE-63.md) |
| [US-WNE-63-6](tasks/US-WNE-63-6.md) | Test: Test Dispose optionally closes underlying socket | ⚪ todo | — |  | — | — | [US-WNE-63](stories/US-WNE-63.md) |
| [US-WNE-63-7](tasks/US-WNE-63-7.md) | Test: Test Stream-based APIs (StreamReader/StreamWriter) work | ⚪ todo | — |  | — | — | [US-WNE-63](stories/US-WNE-63.md) |
| [US-WNE-63-8](tasks/US-WNE-63-8.md) | Scaffold WgNetworkStreamTests with mock socket | ⚪ todo | 1 |  | — | — | [US-WNE-63](stories/US-WNE-63.md) |
| [US-WNE-63-9](tasks/US-WNE-63-9.md) | Implement Read/Write delegation and capability property tests | ⚪ todo | 1 |  | — | US-WNE-63-8 | [US-WNE-63](stories/US-WNE-63.md) |
| [US-WNE-64-1](tasks/US-WNE-64-1.md) | Test: Test WgDevice creation from WgConfig | ✅ done | 1 |  | claude | — | [US-WNE-64](stories/US-WNE-64.md) |
| [US-WNE-64-10](tasks/US-WNE-64-10.md) | Implement WgDevice creation and disposal pattern tests | ✅ done | 2 |  | claude | US-WNE-64-9 | [US-WNE-64](stories/US-WNE-64.md) |
| [US-WNE-64-11](tasks/US-WNE-64-11.md) | Implement CreateSocket and GetStats tests | ✅ done | 2 |  | claude | US-WNE-64-10 | [US-WNE-64](stories/US-WNE-64.md) |
| [US-WNE-64-12](tasks/US-WNE-64-12.md) | Implement multi-device coexistence and live-socket disposal tests | ✅ done | 2 |  | claude | US-WNE-64-11 | [US-WNE-64](stories/US-WNE-64.md) |
| [US-WNE-64-2](tasks/US-WNE-64-2.md) | Test: Test IDisposable pattern works correctly | ✅ done | 1 |  | claude | — | [US-WNE-64](stories/US-WNE-64.md) |
| [US-WNE-64-3](tasks/US-WNE-64-3.md) | Test: Test IAsyncDisposable pattern works correctly | ✅ done | 1 |  | claude | — | [US-WNE-64](stories/US-WNE-64.md) |
| [US-WNE-64-4](tasks/US-WNE-64-4.md) | Test: Test CreateSocket returns valid Socket | ✅ done | 1 |  | claude | — | [US-WNE-64](stories/US-WNE-64.md) |
| [US-WNE-64-5](tasks/US-WNE-64-5.md) | Test: Test GetStats returns tunnel statistics | ✅ done | 1 |  | claude | — | [US-WNE-64](stories/US-WNE-64.md) |
| [US-WNE-64-6](tasks/US-WNE-64-6.md) | Test: Test disposal while sockets are live (ref-counting or exception) | ✅ done | 1 |  | claude | — | [US-WNE-64](stories/US-WNE-64.md) |
| [US-WNE-64-7](tasks/US-WNE-64-7.md) | Test: Test multiple devices coexist independently | ✅ done | 1 |  | claude | — | [US-WNE-64](stories/US-WNE-64.md) |
| [US-WNE-64-8](tasks/US-WNE-64-8.md) | Test: Test double-dispose is safe | ✅ done | 1 |  | claude | — | [US-WNE-64](stories/US-WNE-64.md) |
| [US-WNE-64-9](tasks/US-WNE-64-9.md) | Scaffold WgDeviceTests with mock native device backend | ✅ done | 1 |  | claude | — | [US-WNE-64](stories/US-WNE-64.md) |
| [US-WNE-65-1](tasks/US-WNE-65-1.md) | Test: cargo audit runs in CI (weekly scheduled + on PR) | ⚪ todo | — |  | — | — | [US-WNE-65](stories/US-WNE-65.md) |
| [US-WNE-65-2](tasks/US-WNE-65-2.md) | Test: Cargo.lock committed and pinned | ⚪ todo | — |  | — | — | [US-WNE-65](stories/US-WNE-65.md) |
| [US-WNE-65-3](tasks/US-WNE-65-3.md) | Test: Dependabot configured for Cargo.toml and .csproj | ⚪ todo | — |  | — | — | [US-WNE-65](stories/US-WNE-65.md) |
| [US-WNE-65-4](tasks/US-WNE-65-4.md) | Test: Dependabot PRs for native deps flagged for manual review (not auto-merged) | ⚪ todo | — |  | — | — | [US-WNE-65](stories/US-WNE-65.md) |
| [US-WNE-65-5](tasks/US-WNE-65-5.md) | Test: dotnet list package --vulnerable in CI | ⚪ todo | — |  | — | — | [US-WNE-65](stories/US-WNE-65.md) |
| [US-WNE-65-6](tasks/US-WNE-65-6.md) | Add cargo audit CI workflow (weekly + on PR) | ⚪ todo | 1 |  | — | — | [US-WNE-65](stories/US-WNE-65.md) |
| [US-WNE-65-7](tasks/US-WNE-65-7.md) | Configure Dependabot for Cargo.toml and .csproj | ⚪ todo | 1 |  | — | — | [US-WNE-65](stories/US-WNE-65.md) |
| [US-WNE-65-8](tasks/US-WNE-65-8.md) | Add dotnet vulnerability scanning to CI | ⚪ todo | 1 |  | — | — | [US-WNE-65](stories/US-WNE-65.md) |
| [US-WNE-65-9](tasks/US-WNE-65-9.md) | Test: verify CI workflows catch known vulnerabilities | ⚪ todo | 1 |  | — | US-WNE-65-6, US-WNE-65-8 | [US-WNE-65](stories/US-WNE-65.md) |
| [US-WNE-66-1](tasks/US-WNE-66-1.md) | Test: All buffer operations validate length before access | ✅ done | 1 |  | claude | — | [US-WNE-66](stories/US-WNE-66.md) |
| [US-WNE-66-10](tasks/US-WNE-66-10.md) | Test: null pointer and invalid buffer handling returns error codes | ✅ done | 2 |  | claude | US-WNE-66-7 | [US-WNE-66](stories/US-WNE-66.md) |
| [US-WNE-66-11](tasks/US-WNE-66-11.md) | Test: invalid and stale handle rejection | ✅ done | 1 |  | claude | US-WNE-66-8 | [US-WNE-66](stories/US-WNE-66.md) |
| [US-WNE-66-12](tasks/US-WNE-66-12.md) | Test: rapid create/dispose cycles under thread contention | ✅ done | 2 |  | claude | US-WNE-66-8, US-WNE-66-9 | [US-WNE-66](stories/US-WNE-66.md) |
| [US-WNE-66-2](tasks/US-WNE-66-2.md) | Test: Null pointer checks on all FFI entry points | ✅ done | 1 |  | claude | — | [US-WNE-66](stories/US-WNE-66.md) |
| [US-WNE-66-3](tasks/US-WNE-66-3.md) | Test: Handle validation on every call (invalid handle returns error code not crash) | ✅ done | 1 |  | claude | — | [US-WNE-66](stories/US-WNE-66.md) |
| [US-WNE-66-4](tasks/US-WNE-66-4.md) | Test: Ref-counting prevents use-after-free across device/socket boundary | ✅ done | 2 |  | claude | — | [US-WNE-66](stories/US-WNE-66.md) |
| [US-WNE-66-5](tasks/US-WNE-66-5.md) | Test: IDisposable + CriticalFinalizerObject ensures cleanup | ✅ done | 1 |  | claude | — | [US-WNE-66](stories/US-WNE-66.md) |
| [US-WNE-66-6](tasks/US-WNE-66-6.md) | Test: Test: rapid create/dispose cycles under thread contention — no crashes | ✅ done | 2 |  | claude | — | [US-WNE-66](stories/US-WNE-66.md) |
| [US-WNE-66-7](tasks/US-WNE-66-7.md) | Add null pointer and buffer length validation to all Rust FFI entry points | ✅ done | 2 |  | claude | — | [US-WNE-66](stories/US-WNE-66.md) |
| [US-WNE-66-8](tasks/US-WNE-66-8.md) | Implement handle validation with generational index pattern | ✅ done | 3 |  | claude | US-WNE-66-7 | [US-WNE-66](stories/US-WNE-66.md) |
| [US-WNE-66-9](tasks/US-WNE-66-9.md) | Implement ref-counting for device/socket cross-boundary lifetime | ✅ done | 2 |  | claude | US-WNE-66-8 | [US-WNE-66](stories/US-WNE-66.md) |
| [US-WNE-67-1](tasks/US-WNE-67-1.md) | Test: Cargo.lock committed with pinned versions | ⚪ todo | — |  | — | — | [US-WNE-67](stories/US-WNE-67.md) |
| [US-WNE-67-2](tasks/US-WNE-67-2.md) | Test: Verify boringtun and smoltcp crate checksums | ⚪ todo | — |  | — | — | [US-WNE-67](stories/US-WNE-67.md) |
| [US-WNE-67-3](tasks/US-WNE-67-3.md) | Test: Document approved dependency versions in SECURITY.md | ⚪ todo | — |  | — | — | [US-WNE-67](stories/US-WNE-67.md) |
| [US-WNE-67-4](tasks/US-WNE-67-4.md) | Test: Alerting on new CVEs for pinned dependencies | ⚪ todo | — |  | — | — | [US-WNE-67](stories/US-WNE-67.md) |
| [US-WNE-67-5](tasks/US-WNE-67-5.md) | Test: Review process for dependency version bumps documented | ⚪ todo | — |  | — | — | [US-WNE-67](stories/US-WNE-67.md) |
| [US-WNE-67-6](tasks/US-WNE-67-6.md) | Pin and verify critical crate versions with checksum validation | ⚪ todo | 2 |  | — | — | [US-WNE-67](stories/US-WNE-67.md) |
| [US-WNE-67-7](tasks/US-WNE-67-7.md) | Document approved dependencies and review process in SECURITY.md | ⚪ todo | 1 |  | — | — | [US-WNE-67](stories/US-WNE-67.md) |
| [US-WNE-67-8](tasks/US-WNE-67-8.md) | Configure CVE alerting for pinned dependencies | ⚪ todo | 1 |  | — | — | [US-WNE-67](stories/US-WNE-67.md) |
| [US-WNE-67-9](tasks/US-WNE-67-9.md) | Test: verify checksum validation catches crate substitution | ⚪ todo | 1 |  | — | US-WNE-67-6 | [US-WNE-67](stories/US-WNE-67.md) |
| [US-WNE-7-1](tasks/US-WNE-7-1.md) | Test: Enum or constants for all error codes (WG_OK=0 | ✅ done | — |  | — | — | [US-WNE-7](stories/US-WNE-7.md) |
| [US-WNE-7-10](tasks/US-WNE-7-10.md) | Test: Last-error uses thread-local storage so concurrent callers do not clobber each other | ✅ done | — |  | — | — | [US-WNE-7](stories/US-WNE-7.md) |
| [US-WNE-7-11](tasks/US-WNE-7-11.md) | Define WgError enum and negative integer constants in lib.rs | ✅ done | 1 |  | claude | — | [US-WNE-7](stories/US-WNE-7.md) |
| [US-WNE-7-12](tasks/US-WNE-7-12.md) | Implement wg_last_error() with thread-local storage | ✅ done | 1 |  | claude | — | [US-WNE-7](stories/US-WNE-7.md) |
| [US-WNE-7-13](tasks/US-WNE-7-13.md) | Test error code values and wg_last_error thread safety | ✅ done | 1 |  | claude | US-WNE-7-11, US-WNE-7-12 | [US-WNE-7](stories/US-WNE-7.md) |
| [US-WNE-7-2](tasks/US-WNE-7-2.md) | Test: WG_ERR_INVALID_HANDLE | ✅ done | — |  | — | — | [US-WNE-7](stories/US-WNE-7.md) |
| [US-WNE-7-3](tasks/US-WNE-7-3.md) | Test: WG_ERR_INVALID_CONFIG | ✅ done | — |  | — | — | [US-WNE-7](stories/US-WNE-7.md) |
| [US-WNE-7-4](tasks/US-WNE-7-4.md) | Test: WG_ERR_CONNECT_FAILED | ✅ done | — |  | — | — | [US-WNE-7](stories/US-WNE-7.md) |
| [US-WNE-7-5](tasks/US-WNE-7-5.md) | Test: WG_ERR_WOULD_BLOCK | ✅ done | — |  | — | — | [US-WNE-7](stories/US-WNE-7.md) |
| [US-WNE-7-6](tasks/US-WNE-7-6.md) | Test: WG_ERR_CLOSED | ✅ done | — |  | — | — | [US-WNE-7](stories/US-WNE-7.md) |
| [US-WNE-7-7](tasks/US-WNE-7-7.md) | Test: WG_ERR_BUFFER_TOO_SMALL etc.) with negative integer values | ✅ done | — |  | — | — | [US-WNE-7](stories/US-WNE-7.md) |
| [US-WNE-7-8](tasks/US-WNE-7-8.md) | Test: Error codes are negative integers so zero and positive values can represent success/data | ✅ done | — |  | — | — | [US-WNE-7](stories/US-WNE-7.md) |
| [US-WNE-7-9](tasks/US-WNE-7-9.md) | Test: wg_last_error() returns a null-terminated string describing the most recent error on the calling thread | ✅ done | — |  | — | — | [US-WNE-7](stories/US-WNE-7.md) |
| [US-WNE-8-1](tasks/US-WNE-8-1.md) | Test: Can create smoltcp Interface with a virtual device | ✅ done | 2 |  | claude | — | [US-WNE-8](stories/US-WNE-8.md) |
| [US-WNE-8-2](tasks/US-WNE-8-2.md) | Test: Can open TCP and UDP sockets on the interface | ✅ done | 2 |  | claude | — | [US-WNE-8](stories/US-WNE-8.md) |
| [US-WNE-8-3](tasks/US-WNE-8-3.md) | Test: Can bind/listen/connect/accept TCP sockets | ✅ done | 2 |  | claude | — | [US-WNE-8](stories/US-WNE-8.md) |
| [US-WNE-8-4](tasks/US-WNE-8-4.md) | Test: Socket buffers are correctly sized and configurable | ✅ done | 2 |  | claude | — | [US-WNE-8](stories/US-WNE-8.md) |
| [US-WNE-8-5](tasks/US-WNE-8-5.md) | Test: IP address and routing table configured from WireGuard AllowedIPs | ✅ done | 2 |  | claude | — | [US-WNE-8](stories/US-WNE-8.md) |
| [US-WNE-8-6](tasks/US-WNE-8-6.md) | Implement smoltcp virtual device and Interface creation | ✅ done | 2 |  | claude | — | [US-WNE-8](stories/US-WNE-8.md) |
| [US-WNE-8-7](tasks/US-WNE-8-7.md) | Implement TCP and UDP socket creation and lifecycle | ✅ done | 2 |  | claude | — | [US-WNE-8](stories/US-WNE-8.md) |
| [US-WNE-8-8](tasks/US-WNE-8-8.md) | Implement IP address and route configuration from AllowedIPs | ✅ done | 1 |  | claude | — | [US-WNE-8](stories/US-WNE-8.md) |
| [US-WNE-8-9](tasks/US-WNE-8-9.md) | Test smoltcp socket operations with loopback virtual device | ✅ done | 2 |  | claude | US-WNE-8-6, US-WNE-8-7, US-WNE-8-8 | [US-WNE-8](stories/US-WNE-8.md) |
| [US-WNE-9-1](tasks/US-WNE-9-1.md) | Test: All LibraryImport declarations resolve correctly | ✅ done | 1 |  | claude | US-WNE-9-5, US-WNE-9-6, US-WNE-9-7 | [US-WNE-9](stories/US-WNE-9.md) |
| [US-WNE-9-2](tasks/US-WNE-9-2.md) | Test: Marshalling attributes are correct for all P/Invoke parameters | ✅ done | 1 |  | claude | US-WNE-9-5, US-WNE-9-6, US-WNE-9-7 | [US-WNE-9](stories/US-WNE-9.md) |
| [US-WNE-9-3](tasks/US-WNE-9-3.md) | Test: AOT source generator produces no warnings | ✅ done | 1 |  | claude | US-WNE-9-8 | [US-WNE-9](stories/US-WNE-9.md) |
| [US-WNE-9-4](tasks/US-WNE-9-4.md) | Test: No legacy DllImport usage in codebase | ✅ done | 1 |  | claude | US-WNE-9-8 | [US-WNE-9](stories/US-WNE-9.md) |
| [US-WNE-9-5](tasks/US-WNE-9-5.md) | Declare device lifecycle P/Invoke methods | ✅ done | 2 |  | claude | — | [US-WNE-9](stories/US-WNE-9.md) |
| [US-WNE-9-6](tasks/US-WNE-9-6.md) | Declare socket I/O P/Invoke methods | ✅ done | 2 |  | claude | — | [US-WNE-9](stories/US-WNE-9.md) |
| [US-WNE-9-7](tasks/US-WNE-9-7.md) | Declare peer and key management P/Invoke methods | ✅ done | 1 |  | claude | — | [US-WNE-9](stories/US-WNE-9.md) |
| [US-WNE-9-8](tasks/US-WNE-9-8.md) | Verify AOT source generator compilation | ✅ done | 1 |  | claude | — | [US-WNE-9](stories/US-WNE-9.md) |
