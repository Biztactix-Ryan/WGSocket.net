---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-32-10
points: 2
status: done
story_id: US-WNE-32
tags: []
title: Create FFI test harness with C-calling-convention helpers
updated: '2026-03-27'
---

Build a test harness for FFI boundary tests that: provides a valid wg.conf config string for creating devices; wraps each extern C function (wg_device_new, wg_device_free, wg_connect, wg_close, wg_send, wg_recv, wg_last_error) in safe Rust test helpers that capture return codes; includes helpers for creating null pointers and zero-length slices to pass across the boundary; includes a thread-spawn helper for concurrent FFI call tests. All FFI calls must use unsafe blocks with clear safety comments.