---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-13-6
points: 1
status: todo
story_id: US-WNE-13
tags: []
title: Implement enhanced DllNotFoundException diagnostics
updated: '2026-03-26'
---

Wrap the initial P/Invoke call site (or the resolver) with a try/catch for DllNotFoundException. Rethrow a new DllNotFoundException with a message that includes: the current RuntimeIdentifier, the expected path (runtimes/{rid}/native/wgsocket.{so|dylib|dll}), and a suggestion to install the correct WgSocket.Native.{rid} NuGet package. Include platform-specific file extension in the message (.so for Linux, .dylib for macOS, .dll for Windows).