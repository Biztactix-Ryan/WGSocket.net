---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-24-8
points: 3
status: done
story_id: US-WNE-24
tags: []
title: Implement SendAsync and ReceiveAsync
updated: '2026-03-27'
---

SendAsync(ReadOnlyMemory<byte> buffer, CancellationToken ct = default): validate Connected, pin memory buffer, call NativeMethods.wg_send_async, return ValueTask<int> with bytes sent. ReceiveAsync(Memory<byte> buffer, CancellationToken ct = default): validate Connected, pin buffer, call NativeMethods.wg_recv_async, return ValueTask<int> with bytes received. Use MemoryHandle for pinning. Implement IValueTaskSource<int> for zero-allocation hot path.