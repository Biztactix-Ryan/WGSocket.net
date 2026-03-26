---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-21-6
id: US-WNE-21-8
points: 1
status: todo
story_id: US-WNE-21
tags: []
title: 'Test cbindgen output: verify header contains expected symbols'
updated: '2026-03-26'
---

Write a test (can be a shell script or Rust test) that reads include/wgsocket.h and asserts it contains: wg_device_new, wg_device_free, wg_connect, wg_listen, wg_accept, wg_close, wg_send, wg_recv, wg_get_stats, wg_last_error function declarations, WG_OK and WG_ERR_* constants, WgConfig and WgStats struct definitions, and the WGSOCKET_H include guard.