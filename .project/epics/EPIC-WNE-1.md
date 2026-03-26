---
created: '2026-03-26'
id: EPIC-WNE-1
points: null
priority: must
status: draft
tags:
- rust
- core
- mvp
target_date: null
title: Rust Native Crate Foundation
updated: '2026-03-26'
---

Build the core wgsocket-native Rust crate that composes boringtun (WireGuard crypto) with smoltcp (userspace TCP/IP) into a single cdylib. Includes Cargo.toml setup, boringtun tunnel integration, smoltcp interface wiring, the poll-driven composition engine (tunnel.rs), and the dedicated I/O thread per WgDevice. This is the foundation everything else builds on.