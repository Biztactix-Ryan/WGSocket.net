---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-26-7
id: US-WNE-26-9
points: 1
status: done
story_id: US-WNE-26
tags: []
title: Implement NetworkStream Dispose and ownership semantics
updated: '2026-03-27'
---

Override Dispose(bool disposing): if ownsSocket is true, dispose the underlying socket. Override DisposeAsync(): if ownsSocket, call socket dispose. After disposal, all Read/Write calls throw ObjectDisposedException. Add DataAvailable property (delegates to socket.Available > 0). Add Socket property to expose underlying socket for advanced scenarios.