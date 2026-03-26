---
acceptance_criteria:
- All buffer operations validate length before access
- Null pointer checks on all FFI entry points
- Handle validation on every call (invalid handle returns error code not crash)
- Ref-counting prevents use-after-free across device/socket boundary
- IDisposable + CriticalFinalizerObject ensures cleanup
- 'Test: rapid create/dispose cycles under thread contention — no crashes'
created: '2026-03-26'
epic_id: EPIC-WNE-10
id: US-WNE-66
points: 3
priority: must
status: backlog
tags:
- security
- ffi
- memory-safety
title: Safe memory handling at FFI boundary
updated: '2026-03-26'
---

As a developer, I want all FFI boundary operations to be hardened against invalid inputs (null pointers, bad handles, buffer overflows) so that misuse from the C# side cannot cause crashes, memory corruption, or use-after-free in the native layer.