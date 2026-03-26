---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-62-10
points: 2
status: todo
story_id: US-WNE-62
tags: []
title: Implement fuzz target for wg_send and wg_recv with arbitrary buffers
updated: '2026-03-26'
---

Create fuzz targets for wg_send and wg_recv that exercise arbitrary buffer sizes (0, 1, MTU boundary, oversized), arbitrary contents, null buffer pointers, and mismatched length parameters. Verify graceful error handling with no undefined behavior.