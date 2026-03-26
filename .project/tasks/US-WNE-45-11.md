---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-45-7
- US-WNE-45-8
- US-WNE-45-9
id: US-WNE-45-11
points: 1
status: todo
story_id: US-WNE-45
tags: []
title: Verify cross-compilation for host platform target
updated: '2026-03-26'
---

Run the build script for the current host platform's target. Verify the binary lands in the correct runtimes/{rid}/native/ path with the correct filename. Verify cargo fmt --check and cargo clippy -- -D warnings both exit 0. This validates the script mechanics even though full cross-compilation requires CI runners.