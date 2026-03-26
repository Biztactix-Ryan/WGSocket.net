---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-26-7
- US-WNE-26-8
- US-WNE-26-9
id: US-WNE-26-10
points: 2
status: todo
story_id: US-WNE-26
tags: []
title: Test NetworkStream with mock socket and framework compatibility
updated: '2026-03-26'
---

Write xUnit tests covering: Read/Write delegate to underlying socket, ReadAsync/WriteAsync delegate correctly, CanRead/CanWrite/CanSeek values, Seek throws NotSupportedException, Dispose with ownsSocket=true disposes socket, Dispose with ownsSocket=false leaves socket open, ObjectDisposedException after disposal, DataAvailable property, compatibility test with StreamReader/StreamWriter (string round-trip), compatibility test with BinaryReader/BinaryWriter.