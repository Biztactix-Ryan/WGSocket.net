---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-51-8
id: US-WNE-51-11
points: 1
status: done
story_id: US-WNE-51
tags: []
title: 'Test: Debug/Display output never contains key material'
updated: '2026-04-03'
---

Write tests on both Rust and C# sides that format key-holding types via Debug/Display/ToString and assert the output contains '[REDACTED]' and does not contain any actual key bytes. Cover all key-holding struct types.