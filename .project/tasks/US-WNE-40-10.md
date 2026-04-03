---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-40-7
id: US-WNE-40-10
points: 1
status: done
story_id: US-WNE-40
tags: []
title: 'Test: Clean teardown of multi-peer topology'
updated: '2026-04-03'
---

Write integration test verifying that disposing a WgMeshTopology with 4+ devices cleanly releases all UDP ports, disposes all devices, and does not leave dangling background tasks. Verify no resource leaks by creating and tearing down the topology multiple times.