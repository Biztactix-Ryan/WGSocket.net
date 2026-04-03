---
acceptance_criteria:
- ConnectAsync(IPEndPoint and CancellationToken) returns ValueTask
- AcceptAsync(CancellationToken) returns ValueTask<Socket>
- SendAsync(ReadOnlyMemory<byte> and CancellationToken) returns ValueTask<int>
- ReceiveAsync(Memory<byte> and CancellationToken) returns ValueTask<int>
- All async methods honor CancellationToken for cooperative cancellation
- Async methods do not block threadpool threads (truly async via native callbacks)
created: '2026-03-26'
epic_id: EPIC-WNE-5
id: US-WNE-24
points: 5
priority: must
status: done
tags:
- api
- socket
- async
- mvp
title: WgSocket.Socket asynchronous API
updated: '2026-03-27'
---

As a library consumer, I want async socket methods using ValueTask so that I can build high-performance async applications over WireGuard tunnels without blocking threadpool threads.