---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-12-6
points: 2
status: done
story_id: US-WNE-12
tags: []
title: Implement Span-based send buffer marshalling
updated: '2026-03-26'
---

Create BufferMarshaller.PinAndSend helper that accepts ReadOnlySpan<byte> payload, pins it with fixed statement, passes the pointer and length to NativeMethods.wg_send. Ensure the span is not empty (throw ArgumentException). Return the number of bytes sent. No managed heap allocation should occur in the hot path.