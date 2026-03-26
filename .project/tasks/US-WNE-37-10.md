---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-37-7
id: US-WNE-37-10
points: 2
status: todo
story_id: US-WNE-37
tags: []
title: Implement return code handling and wg_last_error tests
updated: '2026-03-26'
---

Write tests covering every defined error return code from the native layer, verifying each maps to the correct managed handling path (exception, null return, etc.). Test wg_last_error retrieval returns the correct string for the most recent error. Test thread-safety of error retrieval (error from thread A does not leak to thread B). Test behavior when wg_last_error is called with no prior error.