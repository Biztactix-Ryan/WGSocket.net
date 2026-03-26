---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-29-7
points: 1
status: todo
story_id: US-WNE-29
tags: []
title: Implement Socket connection and endpoint properties
updated: '2026-03-26'
---

Add to WgSocket.Socket: Connected property (bool) reflecting internal state machine, set to true after Connect/ConnectAsync succeeds, set to false after Close/error. LocalEndPoint (IPEndPoint?) set after Bind. RemoteEndPoint (IPEndPoint?) set after Connect. Available property (int) calls NativeMethods.wg_available to query bytes ready to read. All properties are thread-safe reads.