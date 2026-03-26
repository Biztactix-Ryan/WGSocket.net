---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-31-5
points: 1
status: todo
story_id: US-WNE-31
tags: []
title: Configure namespace and verify public API surface
updated: '2026-03-26'
---

Ensure all public types (Socket, WgDevice, WgConfig, WgPeer, NetworkStream, WgDeviceStats, WgException) are in the WgSocket namespace. Verify no types leak into sub-namespaces. Add XML doc comments (summary, param, returns, exception, example) to all public members. Set up .editorconfig or analyzer rules to enforce XML doc on public API. Verify InternalsVisibleTo for test project. Review that internal types (NativeMethods, SocketState) are not publicly accessible.