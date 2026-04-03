---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-12-7
id: US-WNE-12-2
points: 1
status: done
story_id: US-WNE-12
tags: []
title: 'Test: Receive operations write to Span and report actual length'
updated: '2026-03-26'
---

Test that BufferMarshaller.Receive writes into a Span<byte> and returns actual bytes received. Verify ArgumentException on empty span. Test WgBufferTooSmallException is thrown when native returns buffer-too-small error code. Verify the span contents match what the mock native layer wrote.