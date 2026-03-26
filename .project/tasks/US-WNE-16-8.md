---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-16-7
id: US-WNE-16-8
points: 2
status: todo
story_id: US-WNE-16
tags: []
title: Implement wg_accept for incoming connections
updated: '2026-03-26'
---

Implement #[no_mangle] extern "C" fn wg_accept(handle: usize, listener_fd: i64) -> i64 that validates both the handle and listener fd, polls the listener for an incoming connection, and returns a new socket fd on success. Returns WG_ERR_WOULD_BLOCK if no connection is pending, WG_ERR_INVALID_HANDLE for bad handle or fd.