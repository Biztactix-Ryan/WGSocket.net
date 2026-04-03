---
acceptance_criteria:
- Test wg_device_new with valid config returns valid handle
- Test wg_device_new with invalid config returns error code
- Test all functions with invalid handle return WG_ERR_INVALID_HANDLE
- Test wg_send/wg_recv with null buffer pointer
- Test wg_send/wg_recv with zero length
- Test double wg_device_free (safe and returns error)
- Test double wg_close (safe and returns error)
- Test concurrent FFI calls from multiple threads
- Test wg_last_error returns correct error string
created: '2026-03-26'
epic_id: EPIC-WNE-6
id: US-WNE-32
points: 3
priority: must
status: done
tags:
- rust
- testing
- ffi
- safety
- unit-test
title: FFI boundary safety tests
updated: '2026-03-27'
---

As a developer, I want tests for every FFI entry point so that I can guarantee the C API handles invalid inputs, null pointers, double-free, and concurrent access safely without undefined behavior.