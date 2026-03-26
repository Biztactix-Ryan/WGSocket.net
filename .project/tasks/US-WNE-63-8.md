---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-63-8
points: 1
status: todo
story_id: US-WNE-63
tags: []
title: Scaffold WgNetworkStreamTests with mock socket
updated: '2026-03-26'
---

Create WgNetworkStreamTests.cs with a mock WgSocket that records all Receive/Send/ReceiveAsync/SendAsync calls and returns configurable data. This enables testing NetworkStream delegation without native code. Include helper methods to create streams in read-only, write-only, and read-write modes.