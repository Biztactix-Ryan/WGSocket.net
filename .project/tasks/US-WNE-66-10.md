---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-66-7
id: US-WNE-66-10
points: 2
status: todo
story_id: US-WNE-66
tags: []
title: 'Test: null pointer and invalid buffer handling returns error codes'
updated: '2026-03-26'
---

Write Rust tests that call every extern C function with null pointers, zero-length buffers, and mismatched length parameters. Assert each returns the correct error code and does not panic or crash. Cover all FFI entry points exhaustively.