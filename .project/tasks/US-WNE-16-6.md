---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-16-6
points: 2
status: todo
story_id: US-WNE-16
tags: []
title: Implement wg_connect for outbound TCP connections
updated: '2026-03-26'
---

Implement #[no_mangle] extern "C" fn wg_connect(handle: usize, addr: *const c_char, port: u16) -> i64 that validates the handle, parses the address string, creates a smoltcp TCP socket, initiates connection to the peer, and returns a socket fd (positive integer) or negative error code. Set last-error on failure with details (e.g. peer not found, connection refused).