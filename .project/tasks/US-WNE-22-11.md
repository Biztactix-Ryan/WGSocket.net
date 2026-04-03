---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-22-9
id: US-WNE-22-11
points: 2
status: done
story_id: US-WNE-22
tags: []
title: Implement Socket.Listen and Socket.Accept
updated: '2026-03-27'
---

Listen(int backlog): validate state is Bound, call NativeMethods.wg_listen with backlog parameter, transition state to Listening. Accept(): validate state is Listening, call NativeMethods.wg_accept (blocking), wrap returned native handle in a new WgSocket.Socket with state Connected, increment parent device ref-count for the new socket. Throw SocketException on failure.