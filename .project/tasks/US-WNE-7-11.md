---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-7-11
points: 1
status: todo
story_id: US-WNE-7
tags: []
title: Define WgError enum and negative integer constants in lib.rs
updated: '2026-03-26'
---

Create a Rust enum (repr(i32)) with all FFI error codes: WG_OK=0, WG_ERR_INVALID_HANDLE=-1, WG_ERR_INVALID_CONFIG=-2, WG_ERR_CONNECT_FAILED=-3, WG_ERR_WOULD_BLOCK=-4, WG_ERR_CLOSED=-5, WG_ERR_BUFFER_TOO_SMALL=-6, WG_ERR_BIND_FAILED=-7, WG_ERR_ACCEPT_FAILED=-8, WG_ERR_UNKNOWN=-99. Export as pub const values for C consumption. Include doc comments explaining each code.