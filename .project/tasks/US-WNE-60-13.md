---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-60-11
id: US-WNE-60-13
points: 2
status: done
story_id: US-WNE-60
tags: []
title: Implement property accessor and state validation tests
updated: '2026-04-03'
---

Write tests for property accessors: Connected returns false initially and true after Connect; LocalEndPoint returns the bound endpoint; RemoteEndPoint returns the connected endpoint; Available returns bytes ready to read. Test Blocking property can be toggled between true and false. Test state validation: Send/Receive before Connect throws InvalidOperationException; operations after Dispose throw ObjectDisposedException.