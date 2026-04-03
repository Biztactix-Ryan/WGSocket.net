---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-12-8
id: US-WNE-12-5
points: 1
status: done
story_id: US-WNE-12
tags: []
title: 'Test: Key material validated as 32-byte ReadOnlySpan and never string-allocated'
updated: '2026-03-26'
---

Test KeyMarshaller.ValidateAndPin accepts exactly 32-byte ReadOnlySpan<byte>. Verify ArgumentException for spans of length 0, 31, 33, and 64. Verify the pinned pointer matches the span data. Confirm via reflection or code review that no ToString or Encoding.GetString calls exist in the key marshalling path. Test that the key bytes are not observable in managed string intern pool.