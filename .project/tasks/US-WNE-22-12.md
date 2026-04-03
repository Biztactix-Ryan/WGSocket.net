---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-22-9
id: US-WNE-22-12
points: 2
status: done
story_id: US-WNE-22
tags: []
title: Implement Socket.Send and Socket.Receive
updated: '2026-03-27'
---

Send(ReadOnlySpan<byte> buffer, SocketFlags flags = SocketFlags.None): validate state is Connected, call NativeMethods.wg_send with buffer pointer and length, return bytes sent. Receive(Span<byte> buffer, SocketFlags flags = SocketFlags.None): validate Connected, call NativeMethods.wg_recv, return bytes received. Handle partial sends/receives. Support Send/Receive overloads matching System.Net.Sockets.Socket (byte[] array versions).