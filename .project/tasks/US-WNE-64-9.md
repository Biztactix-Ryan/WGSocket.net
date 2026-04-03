---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-64-9
points: 1
status: done
story_id: US-WNE-64
tags: []
title: Scaffold WgDeviceTests with mock native device backend
updated: '2026-04-03'
---

Create WgDeviceTests.cs with mock infrastructure for the native device layer. The mock INativeMethodsProxy should simulate device creation (returning a mock handle), socket creation from device, statistics retrieval, and device destruction. Track all native calls for assertion. Include helper methods for creating devices with valid WgConfig instances.