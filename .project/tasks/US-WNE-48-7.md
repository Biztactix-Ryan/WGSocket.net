---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-48-7
points: 2
status: todo
story_id: US-WNE-48
tags: []
title: Create rust-build CI workflow with matrix strategy
updated: '2026-03-26'
---

Create .github/workflows/ci.yml with a rust-build job. Define a matrix with 4 entries: {os: windows-latest, target: x86_64-pc-windows-msvc, rid: win-x64}, {os: ubuntu-latest, target: x86_64-unknown-linux-gnu, rid: linux-x64}, {os: macos-latest, target: x86_64-apple-darwin, rid: osx-x64}, {os: macos-latest, target: aarch64-apple-darwin, rid: osx-arm64}. Trigger on push to main and pull_request to main. Install Rust toolchain via dtolnay/rust-toolchain@stable.