---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-62-8
points: 2
status: todo
story_id: US-WNE-62
tags: []
title: Set up cargo-fuzz project structure and base harness
updated: '2026-03-26'
---

Initialize cargo-fuzz in the native crate with `cargo fuzz init`. Create the fuzz/Cargo.toml with appropriate dependencies (libfuzzer-sys, the native crate). Set up the base harness infrastructure: shared helper functions for generating arbitrary configs, buffers, and handle values. Ensure the fuzz targets can link against the extern C API.