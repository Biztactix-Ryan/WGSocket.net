---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-19-4
id: US-WNE-19-5
points: 1
status: done
story_id: US-WNE-19
tags: []
title: 'Test wg_get_stats: valid stats, null pointer, invalid handle'
updated: '2026-03-26'
---

Write integration tests: (1) create device, call wg_get_stats with valid pointer, verify fields are populated with sane defaults (bytes_tx/rx >= 0, peer_count matches config), (2) wg_get_stats with null pointer returns error, (3) wg_get_stats with invalid handle returns WG_ERR_INVALID_HANDLE, (4) verify WgStats struct has expected size and alignment for C interop.