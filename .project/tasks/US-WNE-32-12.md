---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-32-10
id: US-WNE-32-12
points: 3
status: done
story_id: US-WNE-32
tags: []
title: Implement FFI null-pointer, double-free, and concurrency tests
updated: '2026-03-27'
---

Write tests that: call wg_send with a null buffer pointer and verify it returns an error (not a crash); call wg_recv with a null buffer pointer and verify safe error return; call wg_send and wg_recv with zero-length buffers and verify graceful handling; call wg_device_free twice on the same handle and verify the second call returns an error without UB; call wg_close twice on the same connection and verify safe error return; spawn multiple threads that concurrently call FFI functions on the same handle and verify no data races or panics (run under cargo test with --release and RUST_TEST_THREADS).