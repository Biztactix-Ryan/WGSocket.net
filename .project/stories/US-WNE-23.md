---
acceptance_criteria:
- Test valid wg.conf with single peer
- Test valid wg.conf with multiple peers
- Test all optional fields (PresharedKey PersistentKeepalive DNS)
- Test malformed base64 keys (wrong length and invalid chars)
- Test invalid CIDR (missing prefix and out of range)
- Test malformed endpoints
- Test missing required fields
- Test comment and whitespace handling
- Test config builder produces equivalent output
created: '2026-03-26'
epic_id: EPIC-WNE-6
id: US-WNE-23
points: 3
priority: must
status: done
tags:
- rust
- testing
- config
- unit-test
title: Config parsing unit tests
updated: '2026-03-27'
---

As a developer, I want comprehensive unit tests for wg.conf parsing so that I can be confident config handling covers all valid formats, edge cases, and error conditions.