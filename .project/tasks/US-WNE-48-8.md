---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-48-8
points: 1
status: todo
story_id: US-WNE-48
tags: []
title: Add Rust quality checks to each matrix leg
updated: '2026-03-26'
---

In each rust-build matrix leg, add steps: (1) cargo fmt --check, (2) cargo clippy --target ${{ matrix.target }} -- -D warnings, (3) cargo test --target ${{ matrix.target }} (skip for cross-compiled targets where tests cannot run), (4) cargo build --release --target ${{ matrix.target }}. Use working-directory: src/wgsocket-native for all cargo commands.