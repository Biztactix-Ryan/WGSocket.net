---
acceptance_criteria:
- wg_send copies data from caller buffer into smoltcp socket send buffer and returns
  bytes actually sent
- wg_recv copies data from smoltcp socket receive buffer to caller buffer and returns
  bytes actually received
- Both functions handle partial transfers by returning the actual byte count transferred
- WG_ERR_WOULD_BLOCK is returned when the socket is not ready for send or receive
- Null buffer pointer or zero length is handled safely returning appropriate error
  code
created: '2026-03-26'
epic_id: EPIC-WNE-3
id: US-WNE-18
points: 3
priority: must
status: done
tags:
- ffi
- mvp
- data-transfer
title: Data transfer FFI (wg_send / wg_recv)
updated: '2026-03-26'
---

As a C/C# consumer, I want to send and receive byte data over tunnel sockets through the FFI so that I can exchange application-level payloads across the WireGuard overlay network.