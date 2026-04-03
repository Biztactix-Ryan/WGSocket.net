---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-1-5
- US-WNE-1-6
- US-WNE-1-7
id: US-WNE-1-8
points: 1
status: done
story_id: US-WNE-1
tags: []
title: Verify cdylib builds and test suite runs on all targets
updated: '2026-03-26'
---

Run cargo build and confirm .so/.dll/.dylib is produced. Run cargo test and confirm empty test suite passes. Verify the shared library exports the no-op C function symbol using nm or similar tool. Document the build output paths for each platform in a code comment.