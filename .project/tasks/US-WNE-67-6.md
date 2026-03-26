---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-67-6
points: 2
status: todo
story_id: US-WNE-67
tags: []
title: Pin and verify critical crate versions with checksum validation
updated: '2026-03-26'
---

Ensure Cargo.lock is committed and tracked. Pin exact versions for boringtun and smoltcp in Cargo.toml using '=' version requirements. Create a CI script that extracts checksums for these crates from Cargo.lock and compares against known-good values stored in a checksums file. Fail CI if checksums drift without explicit update.