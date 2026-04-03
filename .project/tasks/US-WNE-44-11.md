---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-44-8
id: US-WNE-44-11
points: 2
status: done
story_id: US-WNE-44
tags: []
title: 'Test: Abrupt disconnect during active transfer'
updated: '2026-03-29'
---

Write integration test where a device is disposed while a large transfer is in progress. Verify the other side receives an error (not a hang). Verify no unhandled exceptions escape. Verify resources are cleaned up despite the abrupt termination. Test both client-side and server-side disposal.