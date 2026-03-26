---
acceptance_criteria:
- WgDeviceHandle extends SafeHandle for device lifetime management
- WgSocketHandle extends SafeHandle for socket fd lifetime
- ReleaseHandle calls wg_device_free and wg_close respectively
- Prevent use-after-dispose via ObjectDisposedException
- CriticalFinalizerObject ensures cleanup even on abrupt termination
created: '2026-03-26'
epic_id: EPIC-WNE-4
id: US-WNE-10
points: 3
priority: must
status: backlog
tags:
- interop
- safehandle
- mvp
title: Safe handle wrappers
updated: '2026-03-26'
---

As a library developer, I want SafeHandle subclasses for WireGuard device handles and socket file descriptors so that native resource lifetimes are managed deterministically and prevent use-after-free bugs.