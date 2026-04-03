---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-12-6
id: US-WNE-12-1
points: 1
status: done
story_id: US-WNE-12
tags: []
title: 'Test: Send operations accept ReadOnlySpan and pin correctly'
updated: '2026-03-26'
---

Test that BufferMarshaller.PinAndSend accepts a ReadOnlySpan<byte> and passes the pinned pointer to the native send function. Verify ArgumentException on empty span. Verify the returned byte count matches the native return value. Use a mock native layer to capture the pointer and length arguments and verify they match the input span.