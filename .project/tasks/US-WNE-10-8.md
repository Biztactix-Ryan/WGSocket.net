---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-10-8
points: 1
status: todo
story_id: US-WNE-10
tags: []
title: Wire SafeHandles into NativeMethods P/Invoke signatures
updated: '2026-03-26'
---

Update NativeMethods.cs P/Invoke declarations to use WgDeviceHandle and WgSocketHandle as parameter/return types instead of raw IntPtr where the runtime should track ownership. Functions that create handles use out parameters or return the SafeHandle. Functions that consume handles take the SafeHandle directly so the runtime prevents collection during the call.