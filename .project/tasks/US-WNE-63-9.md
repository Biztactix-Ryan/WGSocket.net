---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-63-8
id: US-WNE-63-9
points: 1
status: todo
story_id: US-WNE-63
tags: []
title: Implement Read/Write delegation and capability property tests
updated: '2026-03-26'
---

Write tests verifying Read(byte[], int, int) delegates to Socket.Receive with correct parameters and returns the byte count. Write tests verifying Write(byte[], int, int) delegates to Socket.Send. Test ReadAsync and WriteAsync delegate to the async socket counterparts. Assert CanRead is true, CanWrite is true, and CanSeek is false. Test that Seek, Length, and Position throw NotSupportedException.