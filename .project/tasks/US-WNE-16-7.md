---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-16-6
id: US-WNE-16-7
points: 2
status: done
story_id: US-WNE-16
tags: []
title: Implement wg_listen for binding a TCP listener
updated: '2026-03-26'
---

Implement #[no_mangle] extern "C" fn wg_listen(handle: usize, addr: *const c_char, port: u16) -> i64 that validates the handle, parses the bind address, creates a smoltcp TCP listener socket bound to the tunnel address and port, and returns a listener fd or negative error code. Address reuse and port conflict should return WG_ERR_BIND_FAILED.