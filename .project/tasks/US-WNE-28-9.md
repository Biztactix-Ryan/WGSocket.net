---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-28-6
- US-WNE-28-7
- US-WNE-28-8
id: US-WNE-28-9
points: 2
status: done
story_id: US-WNE-28
tags: []
title: Test I/O thread lifecycle and thread-safe socket access
updated: '2026-03-27'
---

Test that creating a WgDevice spawns exactly one thread (check thread count). Test that dropping the WgDevice causes the thread to exit within a reasonable timeout (100ms). Test that creating multiple WgDevices spawns independent threads. Test thread-safe access: spawn multiple application threads that simultaneously read/write to sockets on the same device without data corruption or deadlock. Test that the poll loop correctly processes packets by sending data through a real UDP loopback and verifying it flows through the composition engine.