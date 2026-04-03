---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-11-6
id: US-WNE-11-3
points: 1
status: done
story_id: US-WNE-11
tags: []
title: 'Test: Native error string from wg_last_error included in exception message'
updated: '2026-03-26'
---

Mock wg_last_error to return a known error string. Call ThrowIfError with a negative code. Verify the thrown exception's Message property contains the native error string. Test with null/empty native error string to verify graceful fallback. Test the context overload includes the call-site context in the message.