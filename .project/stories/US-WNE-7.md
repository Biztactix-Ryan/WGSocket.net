---
acceptance_criteria:
- Enum or constants for all error codes (WG_OK=0
- WG_ERR_INVALID_HANDLE
- WG_ERR_INVALID_CONFIG
- WG_ERR_CONNECT_FAILED
- WG_ERR_WOULD_BLOCK
- WG_ERR_CLOSED
- WG_ERR_BUFFER_TOO_SMALL etc.) with negative integer values
- Error codes are negative integers so zero and positive values can represent success/data
- wg_last_error() returns a null-terminated string describing the most recent error
  on the calling thread
- Last-error uses thread-local storage so concurrent callers do not clobber each other
created: '2026-03-26'
epic_id: EPIC-WNE-3
id: US-WNE-7
points: 2
priority: must
status: done
tags:
- ffi
- mvp
- error-handling
title: Error code definitions & conventions
updated: '2026-03-26'
---

As a C/C# consumer of the WgSocket FFI layer, I want a well-defined set of error codes and a last-error retrieval function so that I can diagnose failures without guessing at integer meanings.