---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-24-7
points: 3
status: done
story_id: US-WNE-24
tags: []
title: Implement ConnectAsync and AcceptAsync
updated: '2026-03-27'
---

ConnectAsync(IPEndPoint remoteEP, CancellationToken ct = default): validate state, call NativeMethods.wg_connect_async which returns a native callback handle, wrap in ValueTask using IValueTaskSource pattern, register ct for cancellation via NativeMethods.wg_cancel. AcceptAsync(CancellationToken ct = default): validate Listening state, call NativeMethods.wg_accept_async, wrap result in ValueTask<Socket>. Both must not block threadpool threads.