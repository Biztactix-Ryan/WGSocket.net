---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-28-7
points: 3
status: todo
story_id: US-WNE-28
tags: []
title: Implement non-blocking poll loop with timer integration
updated: '2026-03-26'
---

In the I/O thread, implement the main poll loop. Set the real UDP socket to non-blocking mode. Each iteration: (1) try recv on UDP socket, feed any data to inbound path, (2) call smoltcp Interface::poll() to process timers and pending socket operations, (3) drain outbound packets from the virtual device through boringtun and send on UDP socket, (4) call boringtun update_timers(). Use mio or poll/epoll for efficient waiting (avoid busy-spinning). Calculate the next wakeup time from smoltcp's poll_delay() and boringtun timer requirements.