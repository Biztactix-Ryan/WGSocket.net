---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-14-6
- US-WNE-14-7
- US-WNE-14-8
id: US-WNE-14-9
points: 2
status: done
story_id: US-WNE-14
tags: []
title: 'Test device lifecycle: create, free, double-free, invalid config'
updated: '2026-03-26'
---

Write Rust integration tests: (1) wg_device_new with valid config returns positive handle, (2) wg_device_free with valid handle returns WG_OK, (3) wg_device_free with same handle again returns WG_ERR_INVALID_HANDLE, (4) wg_device_new with null pointer returns WG_ERR_INVALID_CONFIG, (5) wg_device_new with malformed config returns WG_ERR_INVALID_CONFIG and wg_last_error has descriptive message, (6) wg_device_new_from_struct with valid struct returns positive handle.