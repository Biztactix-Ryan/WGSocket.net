---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-33-9
id: US-WNE-33-10
points: 1
status: todo
story_id: US-WNE-33
tags: []
title: Implement WgConfig and WgPeer happy-path construction tests
updated: '2026-03-26'
---

Write tests verifying WgConfig can be constructed with valid private key, listen port, and peer list. Write tests verifying WgPeer can be constructed with valid public key, optional PSK, endpoint, allowed IPs, and keepalive interval. Assert all properties are correctly assigned after construction. Cover both parameterized constructor and builder/object-initializer patterns.