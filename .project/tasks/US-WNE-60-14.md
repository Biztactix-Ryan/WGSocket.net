---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-60-12
id: US-WNE-60-14
points: 2
status: done
story_id: US-WNE-60
tags: []
title: Implement disposal and CancellationToken tests
updated: '2026-04-03'
---

Write tests verifying Close() and Dispose() release underlying native resources via the mock (release callback invoked). Test that Connected returns false after disposal. Test that CancellationToken cancellation in ConnectAsync, AcceptAsync, SendAsync, and ReceiveAsync throws OperationCanceledException. Test pre-cancelled tokens throw immediately without calling native code.