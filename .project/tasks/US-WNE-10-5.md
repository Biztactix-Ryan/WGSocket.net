---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-10-6
- US-WNE-10-7
id: US-WNE-10-5
points: 1
status: todo
story_id: US-WNE-10
tags: []
title: 'Test: CriticalFinalizerObject cleanup guarantee'
updated: '2026-03-26'
---

Verify that SafeHandle subclasses inherit CriticalFinalizerObject behavior. Test that the handle type is assignable to CriticalFinalizerObject via reflection. Create a handle, drop all managed references without calling Dispose, force GC.Collect and GC.WaitForPendingFinalizers, then verify the native free function was called (via a test counter or mock).