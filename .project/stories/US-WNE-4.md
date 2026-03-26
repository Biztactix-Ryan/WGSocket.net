---
acceptance_criteria:
- Validates base64 key format and decoded length is exactly 32 bytes for Curve25519
  keys
- Validates CIDR notation in AllowedIPs (valid IP prefix and mask length)
- Validates endpoint format (IP:port or hostname:port)
- Rejects configs missing required fields (PrivateKey and at least one peer with PublicKey)
- Validates listen port range (1-65535)
created: '2026-03-26'
epic_id: EPIC-WNE-2
id: US-WNE-4
points: 3
priority: must
status: backlog
tags:
- rust
- config
- validation
- mvp
title: Config validation
updated: '2026-03-26'
---

As a developer, I want config validation so that invalid configurations fail early with clear errors.