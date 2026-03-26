---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-21-6
id: US-WNE-21-7
points: 1
status: todo
story_id: US-WNE-21
tags: []
title: Commit generated header and add CI staleness check
updated: '2026-03-26'
---

Run cargo build to generate include/wgsocket.h, review the output for correctness (all FFI functions present, proper C types, include guard). Check the header into the repository. Add a CI script (check-header.sh) that runs cbindgen, diffs against the committed header, and fails if they differ -- ensuring developers regenerate the header when FFI signatures change.