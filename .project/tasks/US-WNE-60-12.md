---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-60-10
id: US-WNE-60-12
points: 2
status: done
story_id: US-WNE-60
tags: []
title: Implement server-side and data transfer method signature tests
updated: '2026-04-03'
---

Write tests verifying Bind(IPEndPoint), Listen(int backlog), Accept(), and AcceptAsync(CancellationToken) method signatures exist and follow System.Net.Sockets.Socket conventions. Write tests verifying Send(ReadOnlySpan<byte>), SendAsync(ReadOnlyMemory<byte>, CancellationToken), Receive(Span<byte>), and ReceiveAsync(Memory<byte>, CancellationToken) signatures. Test return types match expectations (int for sync, ValueTask<int> for async).