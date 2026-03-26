---
acceptance_criteria:
- Test NativeMethods declarations compile and link correctly
- Test string marshalling (UTF-8 and null terminator)
- Test buffer pinning during P/Invoke calls
- Test ReadOnlySpan<byte> key parameter marshalling
- Test return code handling for all error codes
- Test wg_last_error string retrieval
created: '2026-03-26'
epic_id: EPIC-WNE-7
id: US-WNE-37
points: 3
priority: must
status: backlog
tags:
- testing
- mvp
- ffi
title: P/Invoke marshalling tests
updated: '2026-03-26'
---

As a developer, I want unit tests covering the P/Invoke marshalling layer so that I can verify native interop declarations, string encoding, buffer management, and error code handling work correctly at the managed/unmanaged boundary.