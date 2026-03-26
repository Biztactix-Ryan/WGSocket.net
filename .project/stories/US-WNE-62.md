---
acceptance_criteria:
- cargo-fuzz harness targeting all extern C functions
- Fuzz wg_device_new with arbitrary config strings
- Fuzz wg_send/wg_recv with arbitrary buffer sizes and contents
- Fuzz wg_connect with arbitrary address/port combinations
- Fuzz handle values (random usize)
- No panics and no segfaults and no undefined behavior under fuzz
- CI integration (nightly or on-demand)
created: '2026-03-26'
epic_id: EPIC-WNE-10
id: US-WNE-62
points: 5
priority: must
status: backlog
tags:
- security
- fuzz
- ffi
title: FFI fuzz testing
updated: '2026-03-26'
---

As a security engineer, I want all extern C FFI entry points fuzz-tested with cargo-fuzz so that memory safety violations, panics, and undefined behavior at the FFI boundary are discovered before they reach production.