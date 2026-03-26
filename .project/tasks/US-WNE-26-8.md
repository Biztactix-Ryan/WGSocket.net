---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-26-8
points: 2
status: todo
story_id: US-WNE-26
tags: []
title: Implement NetworkStream Read/Write and async variants
updated: '2026-03-26'
---

Override Read(byte[] buffer, int offset, int count): delegate to socket.Receive(buffer.AsSpan(offset, count)). Override Write(byte[] buffer, int offset, int count): delegate to socket.Send(buffer.AsSpan(offset, count)). Override ReadAsync(Memory<byte>, CancellationToken): delegate to socket.ReceiveAsync. Override WriteAsync(ReadOnlyMemory<byte>, CancellationToken): delegate to socket.SendAsync. Override the legacy BeginRead/EndRead and BeginWrite/EndWrite using APM pattern wrapping async methods.