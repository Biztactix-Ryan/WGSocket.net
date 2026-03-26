---
created: '2026-03-26'
id: EPIC-WNE-6
points: null
priority: must
status: draft
tags:
- rust
- testing
- mvp
target_date: null
title: Rust Unit & Integration Tests
updated: '2026-03-26'
---

Comprehensive Rust-side test suite. Unit tests for config parsing, packet composition, handle validation, and error paths. Integration tests for boringtun↔smoltcp wiring over loopback — verify that the tunnel composition actually produces valid encrypted WireGuard packets and that smoltcp correctly processes TCP segments. Test the FFI boundary with invalid handles, null pointers, zero-length buffers, and concurrent access.