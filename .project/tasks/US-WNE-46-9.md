---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-46-8
id: US-WNE-46-9
points: 1
status: todo
story_id: US-WNE-46
tags: []
title: Implement handle creation and single-dispose tests
updated: '2026-03-26'
---

Write tests verifying WgDeviceHandle and WgSocketHandle can be created from mock IntPtr values and disposed correctly. Assert that Dispose calls the corresponding native release function exactly once. Assert that IsInvalid returns true for IntPtr.Zero and false for valid handles. Assert that IsClosed transitions from false to true after disposal.