---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-12-6
- US-WNE-12-7
id: US-WNE-12-3
points: 1
status: done
story_id: US-WNE-12
tags: []
title: 'Test: Buffer pinning prevents GC relocation during P/Invoke'
updated: '2026-03-26'
---

Verify that during a simulated P/Invoke call the buffer address remains stable. Allocate a buffer, pin it via the marshalling helper, trigger GC.Collect inside a callback, and verify the pointer has not changed. This tests both the fixed statement and GCHandle pinning paths.