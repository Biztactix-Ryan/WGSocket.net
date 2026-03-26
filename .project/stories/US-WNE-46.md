---
acceptance_criteria:
- Test WgDeviceHandle creation and disposal
- Test WgSocketHandle creation and disposal
- Test double-dispose is safe (no exception and no crash)
- Test dispose order (socket before device)
- Test finalizer fires on GC if not disposed
- Test ObjectDisposedException after dispose
- Test concurrent dispose from multiple threads
created: '2026-03-26'
epic_id: EPIC-WNE-7
id: US-WNE-46
points: 3
priority: must
status: backlog
tags:
- testing
- mvp
- resource-management
title: Safe handle lifecycle tests
updated: '2026-03-26'
---

As a developer, I want unit tests for SafeHandle-derived types (WgDeviceHandle, WgSocketHandle) so that I can verify correct resource lifecycle management, safe disposal ordering, and resilience against misuse patterns like double-dispose and post-dispose access.