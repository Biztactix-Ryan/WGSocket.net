---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-1-5
points: 1
status: todo
story_id: US-WNE-1
tags: []
title: Initialize Cargo project with cdylib crate type
updated: '2026-03-26'
---

Run cargo init --lib for wgsocket-native crate. Configure Cargo.toml with [lib] crate-type = ["cdylib"] and edition = "2021". Add package metadata (name, version, license). Create minimal lib.rs with a single no-op extern "C" fn to validate cdylib linkage.