---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-35-7
points: 2
status: done
story_id: US-WNE-35
tags: []
title: Implement handle validation, ref-counting, and secure cleanup
updated: '2026-03-26'
---

Create a validate_handle(handle) -> Result<Arc<WgDevice>, ErrorCode> function used at every FFI entry point. Return well-defined error codes for invalid handle, already-destroyed device, etc. Use Arc reference counting: each live socket holds an Arc<WgDevice> clone, preventing device teardown while sockets exist. Device::drop() implementation: signal I/O thread shutdown, join thread, then zeroize all sensitive memory (private keys, session keys, preshared keys) using the zeroize crate. Add zeroize as a dependency and derive Zeroize on key-holding structs.