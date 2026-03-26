---
acceptance_criteria:
- Verify initial Noise_IKpsk2 handshake completes successfully
- Verify data flows after handshake
- Verify rekey occurs (force by time or packet count)
- Verify data continues to flow after rekey without interruption
- Verify handshake with PSK (pre-shared key) works correctly
- Test handshake timeout when peer is unreachable
created: '2026-03-26'
epic_id: EPIC-WNE-8
id: US-WNE-43
points: 3
priority: must
status: backlog
tags:
- testing
- integration
- handshake
- crypto
title: Handshake and rekey verification
updated: '2026-03-26'
---

As a developer, I want to verify the Noise_IKpsk2 handshake and automatic rekeying so that I can confirm the cryptographic protocol works correctly through the full stack including PSK support and timeout handling.