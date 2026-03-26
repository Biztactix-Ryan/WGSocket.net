---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-17-7
points: 1
status: todo
story_id: US-WNE-17
tags: []
title: Implement WgConfig configuration model
updated: '2026-03-26'
---

Create the WgConfig class in the WgSocket namespace with properties: PrivateKey (byte[32]), ListenPort (int?), Address (IPAddress), Peers (IReadOnlyList<WgPeer>). Add constructor validation: PrivateKey must be exactly 32 bytes, ListenPort must be 0-65535 if provided, Address must not be null. Support object initializer and builder pattern (WgConfig.Builder). Override ToString() to redact PrivateKey. Include a ToNativeConfig() internal method for FFI layer consumption.