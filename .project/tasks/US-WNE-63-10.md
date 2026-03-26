---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-63-8
id: US-WNE-63-10
points: 1
status: todo
story_id: US-WNE-63
tags: []
title: Implement disposal behavior and StreamReader/StreamWriter integration tests
updated: '2026-03-26'
---

Write tests verifying that Dispose with ownsSocket=true closes the underlying socket, and ownsSocket=false leaves it open. Test that after disposal, Read/Write throw ObjectDisposedException. Write integration tests wrapping the stream in StreamReader and StreamWriter, verifying text can be written and read back through the mock socket pipeline.