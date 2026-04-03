---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-18-6
id: US-WNE-18-7
points: 2
status: done
story_id: US-WNE-18
tags: []
title: Implement wg_recv for reading data from a socket
updated: '2026-03-26'
---

Implement #[no_mangle] extern "C" fn wg_recv(handle: usize, fd: i64, buf: *mut u8, len: usize) -> i64 that validates handle and fd, checks buf is non-null and len > 0, copies up to len bytes from the smoltcp TCP receive buffer into the caller buffer, and returns the number of bytes actually read. Returns WG_ERR_WOULD_BLOCK if no data available, WG_ERR_CLOSED if socket is closed, WG_ERR_INVALID_HANDLE for bad handle/fd.