---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-13-5
id: US-WNE-13-3
points: 1
status: done
story_id: US-WNE-13
tags: []
title: 'Test: Platform RID resolution covers all supported targets'
updated: '2026-03-26'
---

Parameterized test that verifies the resolver produces correct probe paths for win-x64, linux-x64, osx-x64, and osx-arm64. Verify library file extension is correct per platform (.dll, .so, .dylib). Verify fallback RID logic (e.g., linux-musl-x64 falls back to linux-x64).