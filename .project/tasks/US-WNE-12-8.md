---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-12-8
points: 2
status: todo
story_id: US-WNE-12
tags: []
title: Implement UTF-8 config string and key material marshalling
updated: '2026-03-26'
---

Create ConfigMarshaller.ToNativeUtf8 that converts a managed string to a stackalloc'd or rented UTF-8 null-terminated byte buffer for P/Invoke calls. Create KeyMarshaller.ValidateAndPin that accepts ReadOnlySpan<byte> of exactly 32 bytes, throws ArgumentException if wrong length, and returns a pinned pointer for the P/Invoke call. Ensure key bytes are never copied to a managed string or char array. Use ArrayPool<byte> for config strings exceeding stackalloc threshold (256 bytes).