---
created: '2026-03-26'
id: EPIC-WNE-10
points: null
priority: should
status: draft
tags:
- security
- hardening
target_date: null
title: Security Hardening
updated: '2026-03-26'
---

Verify and enforce all security properties defined in the threat model. Key zeroization (zeroize crate on Rust side, SecureString/zeroing on C# side), FFI fuzz testing (cargo fuzz targeting all extern C entry points), cargo audit in CI (weekly scheduled), no-log enforcement for key material (test that private keys and PSKs never appear in any log output at any level), Cargo.lock pinning, Dependabot configuration for both Cargo.toml and .csproj, and cbindgen header drift detection.