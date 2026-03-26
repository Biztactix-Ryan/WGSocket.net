---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-44-8
id: US-WNE-44-9
points: 2
status: todo
story_id: US-WNE-44
tags: []
title: 'Test: Connection refused and non-existent peer'
updated: '2026-03-26'
---

Write integration tests verifying: connecting to a tunnel IP where no listener is active results in a connection refused error (not a hang), and connecting to a peer that was never configured results in an appropriate error within the timeout period. Both cases must not crash or leak resources.