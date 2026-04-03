---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-24-7
- US-WNE-24-8
id: US-WNE-24-9
points: 2
status: done
story_id: US-WNE-24
tags: []
title: Implement async cancellation and timeout support
updated: '2026-03-27'
---

Register CancellationToken callbacks on all async operations to call NativeMethods.wg_cancel on the native async handle. On cancellation, complete the ValueTask with OperationCanceledException. Add ConnectAsync overload with timeout (internal, used by higher-level APIs). Ensure cancelled operations properly clean up native resources. Test that cancellation does not leak native handles.