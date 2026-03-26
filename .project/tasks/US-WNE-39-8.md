---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-39-6
id: US-WNE-39-8
points: 2
status: todo
story_id: US-WNE-39
tags: []
title: 'Test: Multiple concurrent sockets between same peers'
updated: '2026-03-26'
---

Write integration test opening 5-10 concurrent TCP connections between the same two tunnel devices. Each connection sends unique data. Verify all connections complete independently with correct data. Tests that smoltcp's TCP stack correctly multiplexes connections by port.