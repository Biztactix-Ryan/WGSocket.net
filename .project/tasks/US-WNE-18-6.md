---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-18-6
points: 2
status: done
story_id: US-WNE-18
tags: []
title: Implement wg_send for writing data to a socket
updated: '2026-03-26'
---

Implement #[no_mangle] extern "C" fn wg_send(handle: usize, fd: i64, buf: *const u8, len: usize) -> i64 that validates handle and fd, checks buf is non-null and len > 0, copies up to len bytes from the caller buffer into the smoltcp TCP send buffer, and returns the number of bytes actually enqueued. Returns WG_ERR_WOULD_BLOCK if send buffer is full, WG_ERR_CLOSED if socket is closed, WG_ERR_INVALID_HANDLE for bad handle/fd, WG_ERR_BUFFER_TOO_SMALL for null buf.