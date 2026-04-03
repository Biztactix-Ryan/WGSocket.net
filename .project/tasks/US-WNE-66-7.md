---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-66-7
points: 2
status: done
story_id: US-WNE-66
tags: []
title: Add null pointer and buffer length validation to all Rust FFI entry points
updated: '2026-04-03'
---

Audit every #[no_mangle] extern C function. Add null pointer checks for all pointer parameters at the top of each function, returning appropriate error codes. Add buffer length validation before any slice::from_raw_parts or pointer dereference. Use a validation macro or helper to ensure consistency across all entry points.