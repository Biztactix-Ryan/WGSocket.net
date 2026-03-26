---
acceptance_criteria:
- wg_device_new accepts a null-terminated config string (wg.conf format) and returns
  a positive handle on success or negative error code on failure
- wg_device_new accepts a WgConfig struct pointer as an alternative to string config
- wg_device_free releases all resources associated with the handle
- Double-free is safe -- returns WG_ERR_INVALID_HANDLE without crashing or UB
- Config parsing errors are reported via return code and retrievable via wg_last_error
created: '2026-03-26'
epic_id: EPIC-WNE-3
id: US-WNE-14
points: 3
priority: must
status: backlog
tags:
- ffi
- mvp
- lifecycle
title: Device lifecycle FFI (wg_device_new / wg_device_free)
updated: '2026-03-26'
---

As a C/C# consumer, I want to create and destroy WireGuard tunnel devices through the FFI so that I can manage device lifecycle from managed code without memory leaks or crashes.