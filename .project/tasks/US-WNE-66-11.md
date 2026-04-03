---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-66-8
id: US-WNE-66-11
points: 1
status: done
story_id: US-WNE-66
tags: []
title: 'Test: invalid and stale handle rejection'
updated: '2026-04-03'
---

Write tests that call FFI functions with handle value 0, usize::MAX, a handle that was previously freed, and arbitrary random values. Assert all return WG_ERR_INVALID_HANDLE. Verify no crash or UB under AddressSanitizer.