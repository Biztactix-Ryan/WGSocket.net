# Security — WgSocket

## Authentication

WgSocket inherits WireGuard's authentication model entirely — there is no custom auth layer.

**WireGuard's Noise Protocol Framework (Noise_IKpsk2):**
- Each peer has a Curve25519 keypair (private key + public key)
- Peers authenticate each other by knowing each other's public keys in advance (pre-shared key model)
- An optional pre-shared symmetric key (PSK) can be added per-peer for post-quantum resistance
- The handshake produces per-session symmetric keys (ChaCha20-Poly1305) — no long-lived session tokens

**What WgSocket handles:** The library loads WireGuard configuration (private key, peer public keys, endpoints, allowed IPs) from a standard `wg.conf`-format config or programmatic API. Key generation is NOT in scope — consumers use standard `wg genkey` / `wg pubkey` tooling or equivalent.

**What WgSocket does NOT handle:** Key distribution, peer discovery, or certificate management. These are deliberately out of scope — the library operates at the same level as a WireGuard client, not a control plane.

## Authorization

Authorization within the WireGuard tunnel is handled by the **AllowedIPs** mechanism:

- Each peer has an `AllowedIPs` list defining which IP ranges it is permitted to send traffic from and receive traffic to
- This is enforced at the cryptographic layer — packets not matching `AllowedIPs` for the authenticated peer are silently dropped
- There is no application-layer authorization within the library itself; the consumer's application code is responsible for any further access control on top of the tunnel

## Data Classification

| Data Type | Sensitivity | Handling |
|---|---|---|
| WireGuard private keys | **Critical** — compromise breaks all tunnel security | Never stored by the library. Passed in at runtime via config. Never logged at any level. Zeroed from memory when the device is disposed. |
| Peer public keys | **Low** — public by definition | Stored in config, safe to log at debug level. |
| Pre-shared keys (PSK) | **High** — compromise weakens post-quantum resistance | Same handling as private keys. Never logged. Zeroed on dispose. |
| Tunnel traffic (plaintext) | **Depends on consumer** — the library is transport-agnostic | Decrypted in-process memory only. Not buffered to disk. Not logged. |
| Tunnel traffic (encrypted) | **Low** — encrypted with ChaCha20-Poly1305 per-session keys | Transits the single real UDP socket. Safe to capture (that's what WireGuard is designed for). |
| Handshake metadata | **Low** — timing, peer endpoints | May be logged at debug level. No sensitive content. |

## Compliance

None identified. WgSocket is an open-source networking library, not a service handling end-user data. Consumers are responsible for their own compliance obligations. The library facilitates compliance by:

- Using well-audited, standards-based cryptography (WireGuard / Noise Protocol)
- Not persisting any data to disk
- Not phoning home or communicating with any third-party service
- Being fully inspectable (open source, permissive licence)

## Secret Management

The library does not manage secrets. It receives them at runtime:

```csharp
var device = new WgDevice(new WgConfig
{
    PrivateKey = "...",      // Consumer provides this — from vault, env var, etc.
    ListenPort = 51820,
    Peers = new[] { ... }
});
```

**Design constraints:**
- Private key and PSK parameters are accepted as `ReadOnlySpan<byte>` or `SecureString` where feasible, not plain `string`, to reduce copies in managed memory
- The native Rust layer zeroes key material from its allocations when the tunnel is torn down (`zeroize` crate)
- No key material is ever written to log output regardless of log level — this is enforced in code review and tested

## Threat Model

### Attack Surface

1. **The single real UDP socket** — this is the only OS-level network surface. It receives encrypted WireGuard packets from the internet. An attacker can:
   - Send malformed packets → mitigated by boringtun's packet validation (battle-tested, deployed on millions of Cloudflare devices)
   - Replay captured packets → mitigated by WireGuard's anti-replay window (built into the protocol)
   - Flood the socket → mitigated by WireGuard's cookie mechanism for DoS resistance

2. **The C FFI boundary** — unsafe Rust ↔ C ↔ C# P/Invoke. Risks:
   - Buffer overflows if length parameters are incorrect → mitigated by Rust's ownership model on the native side; careful `Span<byte>` usage on the C# side; fuzz testing of the FFI surface
   - Use-after-free if the C# side disposes a device while callbacks are in flight → mitigated by ref-counted handle design in the Rust layer

3. **Memory safety in the managed/unmanaged boundary** — the C# `WgSocket.Socket` holds an opaque handle to a Rust-allocated tunnel. Incorrect disposal ordering could leak or corrupt memory → mitigated by implementing `IDisposable` with release-on-finalizer as a safety net

4. **Supply chain** — boringtun and smoltcp are pulled from crates.io.
   - boringtun is maintained by Cloudflare with a strong security track record
   - smoltcp is widely used in embedded Rust and has been audited in that context
   - `Cargo.lock` is committed to pin exact versions. Dependabot monitors for CVEs.

### Out-of-Scope Threats

- Compromised endpoints (if the machine running WgSocket is owned, the tunnel is irrelevant)
- Side-channel attacks on key material in memory (same exposure as any WireGuard implementation)
- Quantum computing attacks on Curve25519 (WireGuard's PSK option provides mitigation; not a library-level concern)

## Security Tooling

| Tool | Purpose | Integration |
|---|---|---|
| `cargo clippy` | Lint for common Rust footguns | CI — fail on warnings |
| `cargo audit` | Check Rust dependencies for known CVEs | CI — scheduled weekly |
| `cargo fuzz` (planned) | Fuzz the C FFI entry points | CI — nightly or on-demand |
| `dotnet format` | Code style consistency | CI |
| Dependabot | Automated dependency update PRs | GitHub — both Cargo.toml and .csproj |
| `cbindgen` diff check | Ensure C header matches Rust exports | CI — fail if stale |

### Security Review Cadence

- Review the FFI boundary (Rust exports + C# P/Invoke declarations) on every PR that touches it
- Pin and audit boringtun/smoltcp version bumps — don't auto-merge Dependabot PRs for native deps without reviewing the diff
- If the library gains traction, pursue a third-party audit of the ~400-line Rust glue crate (the only novel security-critical code)
