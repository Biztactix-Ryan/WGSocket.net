---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-14-6
id: US-WNE-14-8
points: 1
status: done
story_id: US-WNE-14
tags: []
title: Implement wg_device_free with double-free safety
updated: '2026-03-26'
---

Implement #[no_mangle] extern "C" fn wg_device_free(handle: usize) -> i32 that removes the device from the handle table and drops it. If the handle does not exist (including double-free), return WG_ERR_INVALID_HANDLE and set last-error. Must not panic or trigger undefined behavior on any input.