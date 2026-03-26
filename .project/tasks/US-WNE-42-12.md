---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-42-8
- US-WNE-42-9
- US-WNE-42-10
- US-WNE-42-11
id: US-WNE-42-12
points: 1
status: todo
story_id: US-WNE-42
tags: []
title: Verify local build and test roundtrip
updated: '2026-03-26'
---

Run cargo build --release in src/wgsocket-native/, then dotnet build and dotnet test from repo root. Verify the full local dev loop works end-to-end. Fix any path issues or missing references. Ensure dotnet test discovers and runs xUnit tests.