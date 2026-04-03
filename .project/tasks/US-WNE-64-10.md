---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-64-9
id: US-WNE-64-10
points: 2
status: done
story_id: US-WNE-64
tags: []
title: Implement WgDevice creation and disposal pattern tests
updated: '2026-04-03'
---

Write tests verifying WgDevice can be created from a valid WgConfig (mock returns success handle). Test IDisposable: using block disposes correctly, Dispose calls native destroy exactly once. Test IAsyncDisposable: await using block works, DisposeAsync calls native destroy. Test double-dispose does not throw and does not call native destroy twice. Test operations after dispose throw ObjectDisposedException.