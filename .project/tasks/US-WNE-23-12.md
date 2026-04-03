---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-23-10
id: US-WNE-23-12
points: 1
status: done
story_id: US-WNE-23
tags: []
title: Implement config parsing error-path tests
updated: '2026-03-27'
---

Write unit tests covering all config parsing error conditions: malformed base64 keys (wrong length, invalid characters) return appropriate error; invalid CIDR notation (missing prefix length, prefix out of range like /33) returns error; malformed endpoint strings (missing port, invalid IP) return error; missing required fields (PrivateKey, PublicKey) return error with clear message. Each test should assert the specific error variant, not just that an error occurred.