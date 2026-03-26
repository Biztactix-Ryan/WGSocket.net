---
acceptance_criteria:
- CI step generates wgsocket.h via cbindgen from Rust source
- Generated header is diffed against the checked-in header file
- Build fails with a non-zero exit code if the header is stale (Rust exports changed
  but header not regenerated)
- Error message clearly explains how to regenerate the header locally
- cbindgen.toml configuration checked in and maintained
created: '2026-03-26'
epic_id: EPIC-WNE-9
id: US-WNE-52
points: 2
priority: should
status: backlog
tags:
- ci
- cbindgen
- ffi
title: cbindgen CI staleness check
updated: '2026-03-26'
---

As a maintainer, I want CI to detect when the Rust FFI exports have changed but the C header has not been regenerated so that the .NET P/Invoke bindings never go out of sync with the native library.