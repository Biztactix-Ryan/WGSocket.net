---
acceptance_criteria:
- Helper generates Curve25519 keypairs for tests
- Helper creates two WgDevice instances configured as peers (localhost UDP different
  ports)
- Helper waits for handshake completion with configurable timeout
- Helper provides cleanup/disposal via IAsyncDisposable
- Works in CI with no network access needed beyond localhost
- Harness exposes tunnel IPs and ports for test assertions
created: '2026-03-26'
epic_id: EPIC-WNE-8
id: US-WNE-36
points: 3
priority: must
status: done
tags:
- testing
- integration
- harness
- mvp
title: Integration test harness setup
updated: '2026-03-28'
---

As a developer, I want a reusable test harness that creates paired WgDevice instances so that integration tests can focus on behavior rather than boilerplate setup and teardown.