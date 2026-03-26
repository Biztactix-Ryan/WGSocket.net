---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-24-7
- US-WNE-24-8
- US-WNE-24-9
id: US-WNE-24-10
points: 3
status: todo
story_id: US-WNE-24
tags: []
title: Test Socket async API with cancellation
updated: '2026-03-26'
---

Write xUnit tests covering: ConnectAsync completes successfully, ConnectAsync with cancellation throws OperationCanceledException, AcceptAsync returns connected socket, SendAsync/ReceiveAsync round-trip data, cancellation mid-operation, concurrent async operations on same socket, async operations do not block (verify with SynchronizationContext check), ValueTask can be awaited only once, disposed socket async ops throw ObjectDisposedException.