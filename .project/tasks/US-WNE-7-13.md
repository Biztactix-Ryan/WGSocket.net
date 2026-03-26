---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-7-11
- US-WNE-7-12
id: US-WNE-7-13
points: 1
status: todo
story_id: US-WNE-7
tags: []
title: Test error code values and wg_last_error thread safety
updated: '2026-03-26'
---

Write Rust tests verifying: all error constants are negative, WG_OK is zero, wg_last_error returns null before any error, wg_last_error returns correct string after set_last_error, concurrent threads get independent last-error values (spawn 4 threads, each sets a different error, each reads back its own).