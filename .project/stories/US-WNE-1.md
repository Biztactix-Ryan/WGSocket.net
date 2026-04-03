---
acceptance_criteria:
- Cargo.toml defines cdylib crate type with boringtun and smoltcp dependencies
- cargo build produces platform-appropriate shared library (.so/.dll/.dylib)
- cargo test runs empty test suite successfully
- Crate compiles on Linux and macOS and Windows targets
created: '2026-03-26'
epic_id: EPIC-WNE-1
id: US-WNE-1
points: 3
priority: must
status: done
tags:
- rust
- foundation
- mvp
title: Cargo project setup & dependency wiring
updated: '2026-03-26'
---

As a developer, I want the Rust crate scaffolded with correct Cargo.toml so that boringtun and smoltcp compile as a cdylib.