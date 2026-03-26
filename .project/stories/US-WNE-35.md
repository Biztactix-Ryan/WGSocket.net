---
acceptance_criteria:
- Device instances stored in a global handle map with opaque usize handles
- Handles are validated on every FFI entry point
- Invalid handles return error codes and do not crash
- Ref-counting prevents device teardown while sockets are live
- Device cleanup zeroes sensitive memory (keys and session state)
created: '2026-03-26'
epic_id: EPIC-WNE-1
id: US-WNE-35
points: 3
priority: must
status: backlog
tags:
- rust
- ffi
- safety
- mvp
title: Device & handle management
updated: '2026-03-26'
---

As a developer, I want handle-based device management so that multiple WgDevice instances can coexist safely across the FFI boundary.