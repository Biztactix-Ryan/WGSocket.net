---
acceptance_criteria:
- WgDevice(WgConfig config) creates tunnel via native FFI layer
- Implements IDisposable and IAsyncDisposable for deterministic cleanup
- CreateSocket() factory returns new WgSocket.Socket bound to this device
- GetStats() returns tunnel health metrics (bytes tx/rx and handshake time and peer
  status)
- Ref-counting prevents disposal while sockets are still live
- Finalizer as safety net logs warning if Dispose was not called
created: '2026-03-26'
epic_id: EPIC-WNE-5
id: US-WNE-20
points: 3
priority: must
status: backlog
tags:
- api
- lifecycle
- mvp
title: WgDevice tunnel lifecycle
updated: '2026-03-26'
---

As a library consumer, I want a WgDevice class that manages the WireGuard tunnel lifecycle so that I can create, use, and cleanly dispose of tunnels with deterministic resource management.