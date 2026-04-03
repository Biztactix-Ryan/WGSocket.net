---
acceptance_criteria:
- wg_connect initiates a TCP connection to a peer tunnel address and port and returns
  a socket fd or negative error code
- wg_listen binds and listens on a tunnel address and port and returns a listener
  fd or negative error code
- wg_accept blocks or polls for an incoming connection on a listener fd and returns
  a new socket fd or negative error code
- wg_close closes a socket or listener fd and returns WG_OK or negative error code
- All four functions validate the device handle and fd parameters returning WG_ERR_INVALID_HANDLE
  for bad handles
created: '2026-03-26'
epic_id: EPIC-WNE-3
id: US-WNE-16
points: 5
priority: must
status: done
tags:
- ffi
- mvp
- networking
title: Connection FFI (wg_connect / wg_listen / wg_accept / wg_close)
updated: '2026-03-26'
---

As a C/C# consumer, I want to establish TCP connections, listen for incoming connections, accept peers, and close sockets through the FFI so that I can build networked applications over the WireGuard tunnel.