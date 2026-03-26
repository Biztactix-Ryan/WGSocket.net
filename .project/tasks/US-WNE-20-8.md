---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-20-8
points: 2
status: todo
story_id: US-WNE-20
tags: []
title: Implement WgDevice IDisposable, IAsyncDisposable, and ref-counting
updated: '2026-03-26'
---

Implement IDisposable and IAsyncDisposable on WgDevice. Use a ref-count (Interlocked) incremented by CreateSocket() and decremented when sockets are disposed. Dispose() throws InvalidOperationException if ref-count > 0 (sockets still live). Add finalizer that calls Dispose(false) and logs a warning via Trace if Dispose was never called. DisposeAsync calls the native async shutdown path if available, otherwise wraps sync Dispose in Task.Run.