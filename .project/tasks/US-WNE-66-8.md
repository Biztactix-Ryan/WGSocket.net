---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-66-8
points: 3
status: todo
story_id: US-WNE-66
tags: []
title: Implement handle validation with generational index pattern
updated: '2026-03-26'
---

Replace raw pointer/usize handles with a generational index scheme (slab or slotmap crate). Every handle-accepting FFI function validates the handle exists and has not been freed. Invalid or stale handles return a specific error code (e.g. WG_ERR_INVALID_HANDLE) instead of causing undefined behavior. Freed handles cannot be reused accidentally.