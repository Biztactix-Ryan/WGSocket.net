---
acceptance_criteria:
- Test boringtun encrypt produces valid WireGuard transport messages
- Test boringtun decrypt recovers original plaintext
- Test encrypt-then-decrypt roundtrip preserves data
- Test handshake initiation message format
- Test handshake response message format
- Test anti-replay (duplicate nonce rejected)
- Test timer-driven rekey produces new session
- Test keepalive packets generated correctly
created: '2026-03-26'
epic_id: EPIC-WNE-6
id: US-WNE-25
points: 5
priority: must
status: done
tags:
- rust
- testing
- crypto
- boringtun
- unit-test
title: Packet composition and crypto tests
updated: '2026-03-27'
---

As a developer, I want tests for boringtun packet encryption/decryption and WireGuard message formats so that I can verify the cryptographic layer produces correct WireGuard protocol messages and handles replay protection.