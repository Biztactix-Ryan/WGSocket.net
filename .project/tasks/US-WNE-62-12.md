---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-62-12
points: 2
status: todo
story_id: US-WNE-62
tags: []
title: Implement fuzz target for handle validation with random usize values
updated: '2026-03-26'
---

Create a fuzz target that calls all handle-accepting FFI functions (wg_send, wg_recv, wg_connect, wg_device_free, etc.) with arbitrary usize handle values including 0, usize::MAX, previously-freed handles, and random values. Verify invalid handles return error codes and never cause crashes or use-after-free.