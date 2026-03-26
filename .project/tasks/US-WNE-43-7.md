---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-43-7
points: 2
status: todo
story_id: US-WNE-43
tags: []
title: Implement handshake observation helpers
updated: '2026-03-26'
---

Create helpers to observe and assert handshake state on WgDevice instances. Expose last handshake timestamp, handshake count, current session index, and rekey events. Provide WaitForRekeyAsync(TimeSpan timeout) that detects when a new session key is negotiated. Support PSK configuration on device pairs.