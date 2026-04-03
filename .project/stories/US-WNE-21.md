---
acceptance_criteria:
- cbindgen.toml is configured for C-style header output with appropriate include guard
  and language setting
- build.rs invokes cbindgen to generate wgsocket.h during cargo build
- Generated header includes all extern C function declarations and error code constants
  and struct definitions
- wgsocket.h is checked into the repository at a well-known path (include/wgsocket.h)
- CI step can diff-check the committed header against a freshly generated one to detect
  staleness
created: '2026-03-26'
epic_id: EPIC-WNE-3
id: US-WNE-21
points: 2
priority: must
status: done
tags:
- ffi
- mvp
- build
- ci
title: cbindgen header generation setup
updated: '2026-03-26'
---

As a build engineer, I want cbindgen to automatically generate a C header file from the Rust FFI source so that C and C# consumers always have an up-to-date header that matches the compiled library.