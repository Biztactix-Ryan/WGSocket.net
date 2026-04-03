---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-5-6
- US-WNE-5-7
- US-WNE-5-8
id: US-WNE-5-9
points: 2
status: done
story_id: US-WNE-5
tags: []
title: Test boringtun encrypt/decrypt roundtrip with two tunnel instances
updated: '2026-03-26'
---

Create two boringtun Tunn instances configured as peers of each other (matching key pairs). Drive a full handshake between them by passing packets back and forth. Encrypt a test IP packet through tunnel A, decrypt through tunnel B, and verify the plaintext matches. Test timer-driven rekey by advancing time and verifying new handshake initiates. Verify keepalive packets are generated after idle timeout.