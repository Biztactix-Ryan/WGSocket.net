---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-66-8
id: US-WNE-66-9
points: 2
status: done
story_id: US-WNE-66
tags: []
title: Implement ref-counting for device/socket cross-boundary lifetime
updated: '2026-04-03'
---

Add Arc-based ref-counting to the device and socket objects so that sockets hold a reference to their parent device. Prevent use-after-free by ensuring the device cannot be freed while sockets still reference it. On the C# side, ensure IDisposable ordering is documented and CriticalFinalizerObject is used for the native handle wrapper.