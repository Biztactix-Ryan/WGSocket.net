---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-67-6
id: US-WNE-67-9
points: 1
status: todo
story_id: US-WNE-67
tags: []
title: 'Test: verify checksum validation catches crate substitution'
updated: '2026-03-26'
---

Write a CI test that deliberately modifies a checksum in the known-good checksums file and verifies the CI check fails. Also test that updating Cargo.lock without updating the checksums file is caught. This validates the supply chain verification pipeline works end-to-end.