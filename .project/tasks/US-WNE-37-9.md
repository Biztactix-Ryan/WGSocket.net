---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-37-7
id: US-WNE-37-9
points: 2
status: done
story_id: US-WNE-37
tags: []
title: Implement buffer pinning and Span marshalling tests
updated: '2026-03-27'
---

Write tests verifying that byte buffers are pinned during P/Invoke calls (no GC relocation). Test ReadOnlySpan<byte> key parameters are correctly marshalled to fixed pointers with correct length. Test that oversized and undersized buffers are handled gracefully (expected errors, no memory corruption). Use the mock proxy to validate buffer contents received by native side.