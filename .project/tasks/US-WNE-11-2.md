---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-11-5
- US-WNE-11-6
id: US-WNE-11-2
points: 1
status: done
story_id: US-WNE-11
tags: []
title: 'Test: Correct exception subclass thrown for each error code'
updated: '2026-03-26'
---

Test that ThrowIfError maps each known error code to the correct exception subclass. Use parameterized tests with (errorCode, expectedExceptionType) pairs. Verify unknown negative error codes throw base WgException with the code preserved. Verify positive and zero codes do not throw.