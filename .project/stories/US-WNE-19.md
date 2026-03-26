---
acceptance_criteria:
- wg_get_stats populates a caller-provided WgStats struct with tunnel statistics including
  handshake age and bytes tx/rx and peer count and peer reachability
- Stats struct is C-compatible with repr(C) layout
- wg_last_error returns a null-terminated error string for the most recent error on
  the calling thread (shared implementation with US-WNE-7)
created: '2026-03-26'
epic_id: EPIC-WNE-3
id: US-WNE-19
points: 2
priority: should
status: backlog
tags:
- ffi
- diagnostics
title: Stats and diagnostics FFI
updated: '2026-03-26'
---

As a C/C# consumer, I want to retrieve tunnel statistics and diagnostic information through the FFI so that I can monitor connection health and debug issues from managed code.