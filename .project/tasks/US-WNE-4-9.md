---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-4-6
- US-WNE-4-7
- US-WNE-4-8
id: US-WNE-4-9
points: 2
status: todo
story_id: US-WNE-4
tags: []
title: Tests for config validation
updated: '2026-03-26'
---

Write unit tests for validation: test valid 32-byte base64 key passes; test short/long/non-base64 key fails with InvalidKey; test valid IPv4 and IPv6 CIDRs pass; test invalid CIDR (bad mask, non-IP) fails; test valid IP:port and hostname:port endpoints pass; test invalid endpoints (missing port, port 0, port > 65535) fail; test config with missing private_key is rejected; test config with no peers is rejected; test validate() returns multiple errors simultaneously; test edge cases (port 1, port 65535, /0 CIDR, /32 CIDR).