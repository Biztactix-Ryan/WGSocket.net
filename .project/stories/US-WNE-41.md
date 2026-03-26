---
acceptance_criteria:
- Configure peer with restricted AllowedIPs (e.g. only 10.0.0.1/32)
- Verify traffic to allowed IP succeeds
- Verify traffic to disallowed IP is silently dropped (connection fails or times out)
- Verify packets FROM wrong source IP are dropped
- Test with various CIDR ranges (/32 and /24 and /16 and /0)
created: '2026-03-26'
epic_id: EPIC-WNE-8
id: US-WNE-41
points: 3
priority: must
status: backlog
tags:
- testing
- integration
- security
- allowedips
title: AllowedIPs enforcement test
updated: '2026-03-26'
---

As a developer, I want to verify that the AllowedIPs configuration correctly controls which traffic is accepted and which is dropped so that I can confirm WireGuard's cryptokey routing works correctly through the FFI boundary.