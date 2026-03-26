---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-36-7
points: 1
status: todo
story_id: US-WNE-36
tags: []
title: Implement WgTestKeypair helper for Curve25519 key generation
updated: '2026-03-26'
---

Create a static helper class WgTestKeypair that generates Curve25519 private/public keypair pairs for test use. Uses the same key generation path as production (through Rust FFI or a managed fallback). Returns a record struct with PrivateKey and PublicKey as base64 strings. Must be deterministic-seed-capable for reproducible tests.