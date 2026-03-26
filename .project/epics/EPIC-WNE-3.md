---
created: '2026-03-26'
id: EPIC-WNE-3
points: null
priority: must
status: draft
tags:
- rust
- ffi
- mvp
target_date: null
title: C FFI & Header Generation
updated: '2026-03-26'
---

Define and implement the C ABI exports in lib.rs — the narrow FFI boundary between Rust and C#. Includes: wg_device_new, wg_device_free, wg_connect, wg_listen, wg_accept, wg_send, wg_recv, wg_close, wg_get_stats, and error code definitions. Set up cbindgen to auto-generate wgsocket.h from Rust source. Handle-based opaque pointer design with validation and ref-counting.