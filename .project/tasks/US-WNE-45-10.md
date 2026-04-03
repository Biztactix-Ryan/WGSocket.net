---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-45-10
points: 1
status: done
story_id: US-WNE-45
tags: []
title: Document cross-compilation prerequisites
updated: '2026-03-29'
---

Create or update build documentation covering: required Rust toolchain version, how to install cross-compilation targets via rustup, platform-specific prerequisites (e.g., mingw for Windows cross-compile from Linux, osxcross for macOS from Linux), how to run the build script, and expected output locations. Note that CI handles cross-compilation natively via matrix runners.