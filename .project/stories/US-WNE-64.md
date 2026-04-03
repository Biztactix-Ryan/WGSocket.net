---
acceptance_criteria:
- Test WgDevice creation from WgConfig
- Test IDisposable pattern works correctly
- Test IAsyncDisposable pattern works correctly
- Test CreateSocket returns valid Socket
- Test GetStats returns tunnel statistics
- Test disposal while sockets are live (ref-counting or exception)
- Test multiple devices coexist independently
- Test double-dispose is safe
created: '2026-03-26'
epic_id: EPIC-WNE-7
id: US-WNE-64
points: 3
priority: must
status: done
tags:
- testing
- mvp
- resource-management
title: WgDevice lifecycle tests
updated: '2026-04-03'
---

As a developer, I want unit tests for WgDevice creation, disposal, and socket management so that I can verify the device lifecycle works correctly including IDisposable/IAsyncDisposable patterns, socket creation, statistics retrieval, and safe coexistence of multiple devices.