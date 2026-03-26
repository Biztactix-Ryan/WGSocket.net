---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-46-8
id: US-WNE-46-10
points: 1
status: todo
story_id: US-WNE-46
tags: []
title: Implement double-dispose and post-dispose safety tests
updated: '2026-03-26'
---

Write tests asserting that calling Dispose() twice on WgDeviceHandle and WgSocketHandle does not throw and does not call the native release function a second time. Write tests asserting that using a disposed handle for any operation throws ObjectDisposedException with the handle type name in the message.