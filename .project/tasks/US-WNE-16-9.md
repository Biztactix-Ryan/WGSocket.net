---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-16-6
id: US-WNE-16-9
points: 1
status: todo
story_id: US-WNE-16
tags: []
title: Implement wg_close for socket and listener teardown
updated: '2026-03-26'
---

Implement #[no_mangle] extern "C" fn wg_close(handle: usize, fd: i64) -> i32 that validates handle and fd, closes the socket or listener, removes it from the device's fd table, and returns WG_OK. Invalid handle or fd returns appropriate error code. Closing an already-closed fd returns WG_ERR_INVALID_HANDLE.