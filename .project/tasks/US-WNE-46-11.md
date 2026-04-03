---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-46-8
id: US-WNE-46-11
points: 2
status: done
story_id: US-WNE-46
tags: []
title: Implement disposal ordering and finalizer tests
updated: '2026-03-27'
---

Write tests verifying that when both a WgSocketHandle and its parent WgDeviceHandle are disposed, the socket handle is released before the device handle. Write a test that creates a handle without disposing it, forces GC.Collect and GC.WaitForPendingFinalizers, then verifies the release callback was invoked (finalizer path). Test concurrent Dispose from multiple threads to verify thread-safety (no double-free, no crash).