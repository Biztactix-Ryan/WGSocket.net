---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-10-6
points: 2
status: todo
story_id: US-WNE-10
tags: []
title: Implement WgDeviceHandle SafeHandle subclass
updated: '2026-03-26'
---

Create WgDeviceHandle extending SafeHandle with IsInvalid returning true for IntPtr.Zero. Override ReleaseHandle to call NativeMethods.wg_device_free. Set handleValue via constructor from P/Invoke out parameter. Mark class as sealed. Add ThrowIfDisposed helper that checks IsClosed/IsInvalid and throws ObjectDisposedException with handle type context.