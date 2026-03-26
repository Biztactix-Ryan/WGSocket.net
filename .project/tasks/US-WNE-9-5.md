---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-9-5
points: 2
status: todo
story_id: US-WNE-9
tags: []
title: Declare device lifecycle P/Invoke methods
updated: '2026-03-26'
---

Add LibraryImport declarations for wg_device_new, wg_device_free, wg_device_configure, and wg_device_get_config in NativeMethods.cs. Use IntPtr for opaque handles (consumed by SafeHandle wrappers). Mark string parameters with [MarshalAs(UnmanagedType.LPUTF8Str)] or use raw byte pointers. Ensure partial class and static modifier for source generator compatibility.