---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-9-8
id: US-WNE-9-4
points: 1
status: done
story_id: US-WNE-9
tags: []
title: 'Test: No legacy DllImport usage in codebase'
updated: '2026-03-26'
---

Write a test that scans all .cs source files in the project for [DllImport] attributes and fails if any are found. Use Roslyn source analysis or simple text search. This acts as a regression gate to ensure no one accidentally adds legacy DllImport declarations.