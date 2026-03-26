---
acceptance_criteria:
- Test WgConfig construction with valid parameters
- Test WgPeer construction with valid parameters
- Test validation rejects null/empty private key
- Test validation rejects invalid key length
- Test validation rejects invalid endpoint format
- Test validation rejects invalid CIDR in AllowedIPs
- Test ToString() redacts key material (never shows private key or PSK)
- Test builder/initializer pattern works correctly
created: '2026-03-26'
epic_id: EPIC-WNE-7
id: US-WNE-33
points: 2
priority: must
status: backlog
tags:
- testing
- mvp
title: WgConfig & WgPeer model tests
updated: '2026-03-26'
---

As a developer, I want comprehensive unit tests for the WgConfig and WgPeer model classes so that I can be confident that configuration construction, validation, and security-sensitive string formatting behave correctly.