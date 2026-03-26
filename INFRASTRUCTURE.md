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
│   │   └── Produces BOTH staticlib (.a/.lib) and cdylib (.so/.dll/.dylib)
│   ├── Run csbindgen → generate NativeMethods.g.cs
│   │   └── Fail if generated file differs from checked-in version (drift check)
│   └── Upload native binaries (static + shared) as artefacts
├── Job: dotnet-build (depends on rust-build)
│   ├── Download all 8 native binaries (4 targets × 2 crate types)
│   ├── Place in runtimes/{rid}/native/
│   ├── dotnet build
│   ├── dotnet test (JIT mode — exercises shared library path)
│   ├── dotnet publish -p:PublishAot=true (AOT smoke test — exercises static link path)
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

- `csbindgen` (Cysharp) reads the Rust `extern "C"` functions and auto-generates `NativeMethods.g.cs` with correct `LibraryImport` declarations. This file is checked into the repo and CI fails if it's stale (diff check against regenerated output)
- The generated bindings work identically in both NativeAOT (static link / DirectPInvoke) and JIT (shared library load) modes — no conditional code paths

## Services & Dependencies

### Build-Time Dependencies

| Dependency | Purpose | Licence |
|---|---|---|
| **boringtun** (Rust crate) | WireGuard protocol — handshake, key exchange, packet encrypt/decrypt | BSD-3-Clause |
| **smoltcp** (Rust crate) | Userspace TCP/IP stack — TCP state machine, IP routing, no OS deps | MIT (0-clause) |
| **csbindgen** (Rust crate / build dep) | Auto-generates C# `LibraryImport` P/Invoke declarations from Rust `extern "C"` exports | MIT |

### Runtime Dependencies

None beyond the OS's UDP socket API. The compiled native library is fully self-contained — boringtun and smoltcp are statically linked into the Rust output. In NativeAOT mode, this is further statically linked into the .NET binary itself (single file, zero runtime native deps). In JIT mode, the shared library (`.dll`/`.so`/`.dylib`) is the only runtime native dependency. The NuGet package has no transitive native dependencies.

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
