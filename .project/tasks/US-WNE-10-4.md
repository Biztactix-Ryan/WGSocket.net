---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-10-6
- US-WNE-10-7
- US-WNE-10-8
id: US-WNE-10-4
points: 1
status: done
story_id: US-WNE-10
tags: []
title: 'Test: ObjectDisposedException on use-after-dispose'
updated: '2026-03-26'
---

Dispose a WgDeviceHandle and WgSocketHandle, then attempt to use them in a P/Invoke call (or via the ThrowIfDisposed helper). Verify ObjectDisposedException is thrown with a message identifying the handle type. Test both explicit Dispose and finalization paths where possible.