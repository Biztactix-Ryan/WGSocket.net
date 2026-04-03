---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-20-8
id: US-WNE-20-9
points: 1
status: done
story_id: US-WNE-20
tags: []
title: Implement WgDevice.CreateSocket() and GetStats()
updated: '2026-03-27'
---

CreateSocket() factory method: validates device is not disposed, increments ref-count, creates a new WgSocket.Socket instance bound to this device's tunnel handle, returns it. GetStats() calls NativeMethods.wg_get_stats to retrieve tunnel metrics: BytesSent, BytesReceived, LastHandshakeTime, PeerStatuses. Return a WgDeviceStats record type. Throw ObjectDisposedException if device is disposed.