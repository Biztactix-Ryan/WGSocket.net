---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-39-6
points: 2
status: done
story_id: US-WNE-39
tags: []
title: Implement bidirectional transfer test helper
updated: '2026-03-28'
---

Create a helper that simultaneously sends unique tagged data streams in both directions between two WgDevice tunnel endpoints. Each direction sends a distinct byte pattern (e.g. stream A sends 0xAA-prefixed, stream B sends 0xBB-prefixed). Collects results from both sides for verification. Uses Task.WhenAll for true concurrency.