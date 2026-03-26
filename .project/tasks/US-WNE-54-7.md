---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-54-6
id: US-WNE-54-7
points: 2
status: todo
story_id: US-WNE-54
tags: []
title: Implement error code to exception type mapping tests
updated: '2026-03-26'
---

Write parameterized tests (Theory) that call the exception mapping function with each known error code and assert the correct exception type is returned. Test that exception messages include the native error detail string from wg_last_error. Test WgException.ErrorCode property matches the input code. Test that unknown/undefined error codes produce a generic WgException with the raw code value. Test catch hierarchy: catching WgException catches all subtypes.