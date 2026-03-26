---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-11-6
id: US-WNE-11-4
points: 1
status: todo
story_id: US-WNE-11
tags: []
title: 'Test: ThrowIfError returns cleanly on success codes'
updated: '2026-03-26'
---

Verify ThrowIfError does not throw for return code 0 (success). Verify it does not throw for positive return codes (e.g., bytes-read counts). Verify it throws for -1, -2, and other negative values. Benchmark to confirm no allocation on the success path.