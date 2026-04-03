---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-28-6
points: 2
status: done
story_id: US-WNE-28
tags: []
title: Implement I/O thread spawn and shutdown mechanism
updated: '2026-03-27'
---

Create the WgDevice struct that owns the tunnel composition engine, the real UDP socket, and the smoltcp Interface. On creation, spawn a dedicated std::thread that runs the poll loop. Use an AtomicBool or channel-based shutdown signal so the thread exits cleanly. The thread's JoinHandle is stored on WgDevice. On Drop, signal shutdown and join the thread. Ensure no panic if the thread has already exited.