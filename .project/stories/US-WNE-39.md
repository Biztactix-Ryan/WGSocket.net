---
acceptance_criteria:
- Both peers send data simultaneously in both directions
- Data integrity verified with no corruption and no mixing
- Multiple concurrent sockets between same peers work correctly
- Test under load with many small messages sent rapidly
- All async operations complete without deadlock or timeout
created: '2026-03-26'
epic_id: EPIC-WNE-8
id: US-WNE-39
points: 3
priority: must
status: done
tags:
- testing
- integration
- concurrency
title: Bidirectional concurrent data transfer
updated: '2026-03-28'
---

As a developer, I want to verify that two peers can send and receive data simultaneously in both directions so that I can confirm the tunnel handles full-duplex communication without corruption or data mixing.