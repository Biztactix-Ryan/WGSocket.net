---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-22-10
- US-WNE-22-11
- US-WNE-22-12
- US-WNE-22-13
id: US-WNE-22-14
points: 3
status: done
story_id: US-WNE-22
tags: []
title: Test Socket synchronous API end-to-end
updated: '2026-03-27'
---

Write xUnit tests covering: Connect to valid endpoint succeeds, Connect to invalid endpoint throws SocketException, Bind sets LocalEndPoint, Listen after Bind transitions state, Accept returns connected socket, Send/Receive round-trip data correctly, Close transitions to Closed state, operations on closed socket throw ObjectDisposedException, state validation (Send before Connect throws), Dispose pattern works with using statement. Use mock native layer for unit tests.