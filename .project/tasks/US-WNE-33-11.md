---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-33-9
id: US-WNE-33-11
points: 1
status: todo
story_id: US-WNE-33
tags: []
title: Implement WgConfig and WgPeer validation rejection tests
updated: '2026-03-26'
---

Write tests asserting that WgConfig validation rejects: null private key, empty string private key, keys with incorrect length (not 32 bytes base64), invalid endpoint formats (missing port, invalid IP), and invalid CIDR notation in AllowedIPs (e.g. malformed subnet mask, non-IP text). Each invalid input should throw ArgumentException or a validation-specific exception with a meaningful message.