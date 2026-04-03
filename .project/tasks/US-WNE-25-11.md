---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-25-9
id: US-WNE-25-11
points: 3
status: done
story_id: US-WNE-25
tags: []
title: Implement encrypt/decrypt roundtrip and crypto property tests
updated: '2026-03-27'
---

Write tests that: encrypt a known plaintext and verify the ciphertext is not equal to plaintext; decrypt the ciphertext with the peer tunnel and verify it recovers the original plaintext; run encrypt-then-decrypt roundtrip with various payload sizes (0, 1, 1000, MTU-boundary); test anti-replay by feeding the same encrypted packet twice and verifying the second is rejected; trigger timer-driven rekey by advancing timers and verify a new handshake initiation is produced with a different sender index.