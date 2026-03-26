---
acceptance_criteria:
- cargo build --release works for all 4 targets (x86_64-pc-windows-msvc x86_64-unknown-linux-gnu
  x86_64-apple-darwin aarch64-apple-darwin)
- Cross-compilation toolchains and prerequisites documented in CONTRIBUTING.md or
  build docs
- Output binaries placed in correct runtimes/{rid}/native/ directories matching NuGet
  RID conventions
- Build script or Makefile automates multi-target build with a single command
- cargo fmt --check passes with no formatting violations
- cargo clippy -- -D warnings passes with no warnings
created: '2026-03-26'
epic_id: EPIC-WNE-9
id: US-WNE-45
points: 3
priority: must
status: backlog
tags:
- ci
- rust
- cross-compile
title: Rust cross-compilation setup
updated: '2026-03-26'
---

As a CI pipeline, I want Rust cross-compilation configured for all 4 target platforms so that native binaries are produced for win-x64, linux-x64, osx-x64, and osx-arm64.