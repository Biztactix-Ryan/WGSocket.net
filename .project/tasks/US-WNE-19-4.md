---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-19-4
points: 2
status: todo
story_id: US-WNE-19
tags: []
title: Define WgStats repr(C) struct and implement wg_get_stats
updated: '2026-03-26'
---

Define #[repr(C)] pub struct WgStats with fields: handshake_age_secs (u64), bytes_tx (u64), bytes_rx (u64), peer_count (u32), peers_reachable (u32). Implement #[no_mangle] extern "C" fn wg_get_stats(handle: usize, stats: *mut WgStats) -> i32 that validates handle and stats pointer, populates the struct from the device's tunnel state, and returns WG_OK. Returns WG_ERR_INVALID_HANDLE for bad handle, WG_ERR_BUFFER_TOO_SMALL for null stats pointer.