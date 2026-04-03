---
acceptance_criteria:
- Each WgDevice spawns a dedicated I/O thread
- Poll loop checks real UDP socket for incoming packets using non-blocking I/O
- Poll loop drives smoltcp timers and outbound packet processing
- Thread shuts down cleanly when device is dropped
- Application threads interact via smoltcp socket buffers with thread-safe access
created: '2026-03-26'
epic_id: EPIC-WNE-1
id: US-WNE-28
points: 5
priority: must
status: done
tags:
- rust
- io
- threading
- mvp
title: Poll loop & I/O thread
updated: '2026-03-27'
---

As a developer, I want a dedicated I/O thread with a poll loop so that the tunnel processes packets without blocking application threads.