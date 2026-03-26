# Infrastructure — WgSocket

## Hosting

WgSocket is a library, not a service — there is no production runtime to host. Infrastructure requirements are limited to:

- **Build infrastructure** for cross-compiling the Rust native library to four target triples (`x86_64-pc-windows-msvc`, `x86_64-unknown-linux-gnu`, `x86_64-apple-darwin`, `aarch64-apple-darwin`)
- **NuGet package publishing** to nuget.org (and optionally a private feed for pre-release builds)
- **Test infrastructure** for running integration tests that exercise real WireGuard handshakes over loopback

The source repository is hosted on GitHub under the `Biztactix-Ryan` organisation.

## Environments

| Environment | Purpose | Details |
|---|---|---|
| **Local dev** | Primary development environment | Ryan's workstation. Rust toolchain + .NET 8 SDK. Cargo builds the native lib locally; C# project references it via a local path in the `.csproj` for development. |
| **CI** | Automated build + test | GitHub Actions. Cross-compiles Rust for all four targets, runs `cargo test`, runs `dotnet test`, packages the NuGet `.nupkg`. |
| **NuGet (release)** | Package distribution | Published to nuget.org. The `.nupkg` contains the C# assembly plus native binaries in `runtimes/{rid}/native/` following NuGet's runtime identifier conventions. |

There is no staging or production environment — the library ships as a package consumed by other projects.

## CI/CD

### Build Pipeline (GitHub Actions)

```
Trigger: push to main, PR to main
├── Job: rust-build (matrix: 4 targets)
│   ├── Install Rust toolchain + cross-compilation targets
│   ├── cargo fmt --check
│   ├── cargo clippy -- -D warnings
│   ├── cargo test (on native runner only, not cross targets)
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
|---|---|---|---|
| `win-x64` | `x86_64-pc-windows-msvc` | `windows-latest` | Native MSVC build |
| `linux-x64` | `x86_64-unknown-linux-gnu` | `ubuntu-latest` | Native build |
| `osx-x64` | `x86_64-apple-darwin` | `macos-latest` | Native or cross from arm64 |
| `osx-arm64` | `aarch64-apple-darwin` | `macos-latest` | Native on M-series runners |

Cross-compilation from Linux to Windows/Mac via `cross` is an option if GitHub Actions runner minutes become a concern, but native builds per platform are preferred for reliability.

### Rust Tooling

- `cbindgen` generates the C header (`wgsocket.h`) from the Rust source, ensuring the P/Invoke declarations stay in sync
- The generated header is checked into the repo and CI fails if it's stale (diff check)

## Services & Dependencies

### Build-Time Dependencies

| Dependency | Purpose | Licence |
|---|---|---|
| **boringtun** (Rust crate) | WireGuard protocol — handshake, key exchange, packet encrypt/decrypt | BSD-3-Clause |
| **smoltcp** (Rust crate) | Userspace TCP/IP stack — TCP state machine, IP routing, no OS deps | MIT (0-clause) |
| **cbindgen** (Rust tool) | Generates C headers from Rust `#[no_mangle] extern "C"` exports | MPL-2.0 |

### Runtime Dependencies

None beyond the OS's UDP socket API. The compiled native library is fully self-contained — boringtun and smoltcp are statically linked into the `.dll`/`.so`/`.dylib`. The NuGet package has no transitive native dependencies.

### .NET Dependencies

- `System.Runtime.InteropServices` (in-box) — for `LibraryImport` / P/Invoke
- No third-party NuGet dependencies in the core library (design goal: zero transitive deps)

## Monitoring & Observability

Not applicable for a library. However, the library should:

- Expose structured logging via `Microsoft.Extensions.Logging.ILogger` (optional dependency, passed in by the consumer)
- Surface tunnel health metrics (handshake age, bytes sent/received, peer reachability) via a `WgDevice.GetStats()` API that consumers can wire into their own observability stack
- Never log key material at any log level

## Backup & Recovery

Not applicable. All source is in Git. NuGet packages once published are immutable on nuget.org. No stateful infrastructure exists.
