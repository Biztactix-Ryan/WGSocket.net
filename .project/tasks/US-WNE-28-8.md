---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-28-8
points: 2
status: done
story_id: US-WNE-28
tags: []
title: Implement thread-safe socket buffer access for application threads
updated: '2026-03-27'
---

Design the synchronization boundary between the I/O thread and application threads. The I/O thread owns the smoltcp Interface and polls it. Application threads need to read/write socket buffers. Use a Mutex<Interface> or a lock-free ring buffer approach. Provide send() and recv() methods on a WgSocket handle that acquire the lock, perform the socket operation, and release. Minimize lock contention by keeping critical sections short. Consider using a waker/notify mechanism so the poll loop wakes up when application threads write data.