# WgSocket.net — Infrastructure

WgSocket is a library, not a service — there is no production runtime to host.

## Environments

| Environment | URL | Purpose | Notes |
|------------|-----|---------|-------|
| Local dev | N/A | Primary development | Ryan's workstation. Rust toolchain + .NET 8 SDK. Local cargo build + dotnet build. |
| CI | GitHub Actions | Automated build + test | Cross-compiles Rust for 4 targets, runs cargo test + dotnet test, packages NuGet. |
| NuGet (release) | nuget.org | Package distribution | `.nupkg` with C# assembly + native binaries in `runtimes/{rid}/native/`. |

No staging or production environments — the library ships as a NuGet package consumed by other projects.

## CI/CD

### Build Pipeline (GitHub Actions)

```
Trigger: push to main, PR to main
├── Job: rust-build (matrix: 4 targets)
│   ├── Install Rust toolchain + cross-compilation targets
│   ├── cargo fmt --check
│   ├── cargo clippy -- -D warnings
│   ├── cargo test (native runner only)
│   ├── cargo build --release --target {target}
│   └── Upload native binary as artifact
├── Job: dotnet-build (depends on rust-build)
│   ├── Download all 4 native binaries
│   ├── Place in runtimes/{rid}/native/
│   ├── dotnet build
│   ├── dotnet test
│   └── dotnet pack
└── Job: publish (manual trigger or tag)
    └── dotnet nuget push to nuget.org
```

### Cross-Compilation Targets

| RID | Rust Target | Runner | Notes |
|-----|-------------|--------|-------|
| `win-x64` | `x86_64-pc-windows-msvc` | `windows-latest` | Native MSVC build |
| `linux-x64` | `x86_64-unknown-linux-gnu` | `ubuntu-latest` | Native build |
| `osx-x64` | `x86_64-apple-darwin` | `macos-latest` | Native or cross from arm64 |
| `osx-arm64` | `aarch64-apple-darwin` | `macos-latest` | Native on M-series runners |

### Deployment Process

NuGet package publishing via `dotnet nuget push` — manual trigger or on git tag.

### Rollback Procedure

NuGet packages are immutable once published. To "rollback": publish a new version with the fix, or unlist the broken version on nuget.org.

## Hosting & Services

| Service | Provider | Purpose |
|---------|----------|---------|
| Source control | GitHub (Biztactix-Ryan org) | Repository hosting |
| CI/CD | GitHub Actions | Build, test, package |
| Package registry | nuget.org | NuGet package distribution |

## Monitoring & Alerting

Not applicable for a library. The library exposes:
- Structured logging via `Microsoft.Extensions.Logging.ILogger` (optional, consumer-provided)
- Tunnel health metrics via `WgDevice.GetStats()` — handshake age, bytes sent/received, peer reachability
- No key material logged at any level

## Environment Variables

No environment variables required by the library itself. Consumers provide configuration programmatically.

## Backup & Recovery

Not applicable. All source is in Git. NuGet packages once published are immutable on nuget.org. No stateful infrastructure exists.

## Build-Time Dependencies

| Dependency | Purpose | Licence |
|---|---|---|
| **boringtun** (Rust crate) | WireGuard protocol | BSD-3-Clause |
| **smoltcp** (Rust crate) | Userspace TCP/IP stack | MIT |
| **cbindgen** (Rust tool) | C header generation | MPL-2.0 |

### Runtime Dependencies

None beyond the OS's UDP socket API. The native library is fully self-contained — boringtun and smoltcp are statically linked. No transitive NuGet dependencies.

---
*Last reviewed: 2026-03-26*
*Update this document when infrastructure changes. The daily audit checks for staleness.*
