---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-9-6
points: 2
status: done
story_id: US-WNE-9
tags: []
title: Declare socket I/O P/Invoke methods
updated: '2026-03-26'
---

Add LibraryImport declarations for wg_socket_open, wg_socket_close, wg_send, wg_recv, and wg_poll in NativeMethods.cs. Buffer parameters use unsafe byte* or nint with length parameters. Return values are int error codes. Include [LibraryImport("wgsocket", EntryPoint = "...")] where C function names differ from managed method names.