---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-56-9
id: US-WNE-56-10
points: 2
status: todo
story_id: US-WNE-56
tags: []
title: Implement async chat logic with bidirectional messaging
updated: '2026-03-26'
---

In Program.cs, implement the ChatClient flow: parse or load wg.conf, create and configure WgDevice, create a WgSocket Socket, Connect to the peer's tunnel address and port. Obtain a NetworkStream and run two concurrent async tasks -- one reading from the stream with ReadAsync and printing to console, another reading console input and sending via WriteAsync. Use 'using WgSocket;' as the namespace import. Handle graceful disconnect and Ctrl+C cancellation.