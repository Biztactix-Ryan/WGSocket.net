---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-45-7
points: 2
status: done
story_id: US-WNE-45
tags: []
title: Create cross-compilation build script
updated: '2026-03-29'
---

Create a build script (Makefile or shell script) at repo root that automates building the Rust cdylib for all 4 targets: x86_64-pc-windows-msvc, x86_64-unknown-linux-gnu, x86_64-apple-darwin, aarch64-apple-darwin. Each target should run cargo build --release --target <triple>. Script should accept an optional single-target argument for local dev. Include rustup target add commands for each target.