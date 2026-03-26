---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-5-7
points: 2
status: todo
story_id: US-WNE-5
tags: []
title: Implement encrypt and decrypt paths through boringtun
updated: '2026-03-26'
---

Wire up the boringtun Tunn::encapsulate() method to encrypt plaintext IP packets into WireGuard transport messages. Wire up Tunn::decapsulate() to decrypt incoming WireGuard packets back to plaintext IP packets. Handle the TunnResult variants (WriteToNetwork, WriteToTunnelV4/V6, Done, Err). Provide a clean Rust API: encrypt(plaintext) -> Vec<u8> and decrypt(ciphertext) -> Vec<u8> with proper error handling.