---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-20-7
points: 2
status: todo
story_id: US-WNE-20
tags: []
title: Implement WgDevice constructor and tunnel creation
updated: '2026-03-26'
---

Create the WgDevice class in the WgSocket namespace. Constructor WgDevice(WgConfig config) validates config, calls into the native FFI layer (NativeMethods.wg_create_tunnel) to create a WireGuard tunnel, stores the native handle. Throw WgException on native failure. Store config for later reference. Mark the device as active upon successful creation.