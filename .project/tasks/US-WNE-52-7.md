---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-52-7
points: 1
status: todo
story_id: US-WNE-52
tags: []
title: Add header staleness check script
updated: '2026-03-26'
---

Create a script (scripts/check-header.sh or inline CI step) that: (1) runs cbindgen to generate a temporary header, (2) diffs it against the checked-in include/wgsocket.h, (3) exits non-zero if they differ, (4) prints a clear error message: 'Header is stale. Run: cbindgen --config cbindgen.toml --crate wgsocket-native --output include/wgsocket.h' with the exact command to fix it.