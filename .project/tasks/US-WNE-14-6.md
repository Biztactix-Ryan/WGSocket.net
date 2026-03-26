---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-14-6
points: 2
status: todo
story_id: US-WNE-14
tags: []
title: Implement handle table and wg_device_new with string config
updated: '2026-03-26'
---

Create a global handle table (RwLock<HashMap<usize, WgDevice>>) that maps opaque usize handles to device instances. Implement #[no_mangle] extern "C" fn wg_device_new(config: *const c_char) -> i64 that parses a wg.conf-format string, creates a WgDevice, inserts it into the table, and returns the handle. On parse failure, set last-error and return WG_ERR_INVALID_CONFIG. On null pointer, return WG_ERR_INVALID_CONFIG.