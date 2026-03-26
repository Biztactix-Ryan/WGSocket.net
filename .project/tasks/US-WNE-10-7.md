---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-10-7
points: 2
status: todo
story_id: US-WNE-10
tags: []
title: Implement WgSocketHandle SafeHandle subclass
updated: '2026-03-26'
---

Create WgSocketHandle extending SafeHandle with IsInvalid returning true for -1 (invalid fd) and IntPtr.Zero. Override ReleaseHandle to call NativeMethods.wg_socket_close. On Unix, invalid handle is -1; on Windows, INVALID_HANDLE_VALUE. Include platform-conditional IsInvalid logic. Mark class as sealed.