---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-39-6
id: US-WNE-39-7
points: 2
status: todo
story_id: US-WNE-39
tags: []
title: 'Test: Simultaneous bidirectional TCP data transfer'
updated: '2026-03-26'
---

Write integration test where Device A sends to Device B while Device B simultaneously sends to Device A over separate TCP connections. Verify both streams complete without corruption, data mixing, or deadlock. Test with 64KB payloads in each direction.