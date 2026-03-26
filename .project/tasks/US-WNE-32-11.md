---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-32-10
id: US-WNE-32-11
points: 2
status: todo
story_id: US-WNE-32
tags: []
title: Implement FFI valid-path and error-code tests
updated: '2026-03-26'
---

Write tests that: call wg_device_new with a valid config and verify it returns a positive handle; call wg_device_new with an invalid/empty config and verify it returns the expected error code; call every FFI function (wg_connect, wg_send, wg_recv, wg_close, wg_device_free) with an invalid handle (0, -1, 999999) and verify each returns WG_ERR_INVALID_HANDLE; call wg_last_error after a failed operation and verify it returns a non-null pointer to a meaningful error string.