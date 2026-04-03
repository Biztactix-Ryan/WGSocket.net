---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-12-8
id: US-WNE-12-4
points: 1
status: done
story_id: US-WNE-12
tags: []
title: 'Test: UTF-8 config string marshalling with null termination'
updated: '2026-03-26'
---

Test ConfigMarshaller.ToNativeUtf8 produces a null-terminated UTF-8 byte sequence. Verify ASCII strings, multi-byte UTF-8 characters (e.g., emoji, CJK), and empty strings. Verify that strings exceeding 256 bytes use ArrayPool rental and are returned after use. Verify the null terminator is present at the correct position.