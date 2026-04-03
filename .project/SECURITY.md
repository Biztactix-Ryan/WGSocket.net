# WgSocket.net — Security

## Authentication

WgSocket inherits WireGuard's authentication model entirely — no custom auth layer.

### Method

**WireGuard Noise Protocol Framework (Noise_IKpsk2):**
- Each peer has a Curve25519 keypair (private key + public key)
- Peers authenticate via pre-shared public keys
- Optional pre-shared symmetric key (PSK) per-peer for post-quantum resistance
- Handshake produces per-session symmetric keys (ChaCha20-Poly1305) — no long-lived session tokens

### Token/Session Management

No tokens or sessions. WireGuard handshakes produce ephemeral session keys that rekey automatically every 2 minutes or 2^64 bytes. Key generation is out of scope — consumers use `wg genkey` / `wg pubkey` or equivalent.

### Multi-factor Authentication

Not applicable. Authentication is purely cryptographic (Curve25519 keypairs + optional PSK).

## Authorization

### Roles & Permissions

Authorization is handled by WireGuard's **AllowedIPs** mechanism at the cryptographic layer:

| Mechanism | Scope | Description |
|-----------|-------|-------------|
| AllowedIPs | Per-peer | Defines which IP ranges a peer can send/receive. Packets not matching are silently dropped. |
| Application-layer | Consumer's responsibility | The library provides transport only; further access control is up to the consuming application. |

### Enforcement

AllowedIPs is enforced in the boringtun crypto layer — packets from an authenticated peer that don't match its AllowedIPs list are dropped before reaching smoltcp/application code.

## Data Protection

### Encryption

- **In transit:** All tunnel traffic encrypted with ChaCha20-Poly1305 per-session keys (WireGuard protocol)
- **At rest:** Not applicable — the library does not persist any data to disk

### PII Handling

Not applicable. WgSocket is a transport library — it does not inspect, store, or process application-layer data. PII handling is the consumer's responsibility.

### Data Retention

No data retention. The library operates in-memory only. Decrypted traffic exists only in process memory and is not buffered to disk or logged.

## API Security

Not applicable (library, not a service). The FFI boundary is the "API":
- Opaque handle-based design prevents use-after-free
- Length parameters validated on Rust side before buffer access
- No network-facing API beyond the single encrypted UDP socket

## Secrets Management

The library does not manage secrets. It receives them at runtime:

```csharp
var device = new WgDevice(new WgConfig
{
    PrivateKey = "...",      // From vault, env var, etc.
    ListenPort = 51820,
    Peers = new[] { ... }
});
```

**Design constraints:**
- Private key and PSK accepted as `ReadOnlySpan<byte>` or `SecureString` where feasible (not plain `string`)
- Rust layer zeroes key material on teardown (`zeroize` crate)
- No key material logged at any log level — enforced in code review and tested

## Known Risks & Mitigations

| Risk | Severity | Mitigation | Status |
|------|----------|------------|--------|
| Malformed packets on UDP socket | Medium | boringtun's battle-tested packet validation (deployed on millions of Cloudflare devices) | Mitigated |
| Replay attacks | Low | WireGuard's built-in anti-replay window | Mitigated |
| DoS flooding on UDP socket | Medium | WireGuard's cookie mechanism for DoS resistance | Mitigated |
| Buffer overflow at FFI boundary | High | Rust ownership model + `Span<byte>` on C# side + planned fuzz testing | In progress |
| Use-after-free across FFI | High | Ref-counted handle design in Rust layer + `IDisposable` with release-on-finalizer | Mitigated |
| Supply chain (boringtun/smoltcp) | Medium | `Cargo.lock` pinned, Dependabot monitoring, manual review of native dep bumps | Active |

## Incident Response

Not applicable for a library. Consumers handle their own incident response. Security issues in the library itself should be reported via GitHub security advisories.

## Code Review Checklist

Security-critical items that must be verified during code review:

### No-Log Enforcement for Secrets

**Requirement:** Private keys, pre-shared keys (PSKs), and any derived key material must NEVER appear in log output at any level (Trace through Critical).

**Checklist:**
- [ ] New/modified log statements do not include `PrivateKey`, `Psk`, `PresharedKey`, or similar fields
- [ ] Structured logging fields containing key material use `[Redacted]` or are excluded entirely
- [ ] Debug/trace logs for crypto operations log only public identifiers (peer public key fingerprint, not the key itself)
- [ ] Error messages involving keys show only the operation that failed, not the key value
- [ ] Test coverage exists for log redaction (see `US-WNE-59` acceptance criteria)

**Why:** Key material in logs can leak through log aggregators, error reporting services, diagnostics, or telemetry — compromising tunnel security.

## Security Tooling

| Tool | Purpose | Integration |
|------|---------|-------------|
| `cargo clippy` | Lint for Rust footguns | CI — fail on warnings |
| `cargo audit` | Rust dependency CVE check | CI — weekly |
| `cargo fuzz` (planned) | Fuzz FFI entry points | CI — nightly |
| `cbindgen` diff check | Ensure C header matches Rust exports | CI — fail if stale |
| Dependabot | Automated dependency update PRs | GitHub — Cargo.toml + .csproj |

---
*Last reviewed: 2026-03-26*
*Update this document when security posture changes. The daily audit checks for staleness.*
