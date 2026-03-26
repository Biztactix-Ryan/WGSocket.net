---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-60-10
id: US-WNE-60-11
points: 1
status: todo
story_id: US-WNE-60
tags: []
title: Implement constructor and connection method signature tests
updated: '2026-03-26'
---

Write tests verifying the Socket constructor creates a valid instance with correct default property values. Test Connect(IPEndPoint) and ConnectAsync(IPEndPoint, CancellationToken) method signatures exist and are callable. Test Connect sets the Connected property to true (via mock). Test ConnectAsync returns a ValueTask. Test constructor rejects invalid arguments (null config, etc.).