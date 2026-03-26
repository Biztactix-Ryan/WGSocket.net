---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-20-7
- US-WNE-20-8
- US-WNE-20-9
id: US-WNE-20-10
points: 2
status: todo
story_id: US-WNE-20
tags: []
title: Test WgDevice lifecycle, ref-counting, and stats
updated: '2026-03-26'
---

Write xUnit tests covering: device creation with valid config, device creation failure with invalid config, IDisposable pattern (using statement), IAsyncDisposable pattern (await using), ref-counting prevents premature disposal, disposal after all sockets closed succeeds, GetStats returns valid metrics, double-dispose is safe (no-op), ObjectDisposedException after disposal. Use mock/fake native layer.