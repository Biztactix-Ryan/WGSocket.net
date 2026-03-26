---
acceptance_criteria:
- Test connection refused when no listener is active
- Test connection to non-existent peer
- Test clean disconnect via FIN handshake
- Test abrupt disconnect when device is disposed during active transfer
- Test reconnect after disconnect
- Test socket reuse after close
- Test timeout on blocked receive
created: '2026-03-26'
epic_id: EPIC-WNE-8
id: US-WNE-44
points: 3
priority: must
status: backlog
tags:
- testing
- integration
- error-handling
- lifecycle
title: Connection lifecycle and error handling tests
updated: '2026-03-26'
---

As a developer, I want to verify that connection lifecycle events and error conditions are handled correctly so that I can confirm the library is robust under adverse conditions and provides clear error behavior.