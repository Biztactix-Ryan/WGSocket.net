---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-64-11
id: US-WNE-64-12
points: 2
status: done
story_id: US-WNE-64
tags: []
title: Implement multi-device coexistence and live-socket disposal tests
updated: '2026-04-03'
---

Write tests verifying two WgDevice instances can coexist independently -- disposing one does not affect the other. Test that disposing a device while sockets created from it are still live either: (a) disposes those sockets via ref-counting, or (b) throws InvalidOperationException indicating live sockets exist. Verify no resource leaks by checking all native destroy callbacks fire for both devices and their sockets.