---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-55-9
id: US-WNE-55-10
points: 2
status: done
story_id: US-WNE-55
tags: []
title: Implement WgDevice setup and echo loop logic
updated: '2026-04-03'
---

In Program.cs, implement the full EchoServer flow: parse or load wg.conf, create and configure WgDevice, create a WgSocket Socket, call Listen on the tunnel address, Accept incoming connections, and run an echo loop that reads bytes and writes them back. Use 'using WgSocket;' as the sole namespace import to showcase the single-file experience. Handle graceful shutdown via Ctrl+C/CancellationToken.