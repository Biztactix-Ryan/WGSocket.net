---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-22-13
points: 1
status: todo
story_id: US-WNE-22
tags: []
title: Implement Socket.Close and Dispose
updated: '2026-03-26'
---

Close(): if not already closed, call NativeMethods.wg_close on the native handle, transition state to Closed, decrement parent WgDevice ref-count. Dispose() calls Close(). Implement Dispose(bool disposing) pattern. Suppress finalizer in Dispose. Ensure double-close is safe (no-op). Clear endpoint properties on close.