---
acceptance_criteria:
- Pipeline triggers on push to main and pull_request to main
- 'rust-build job uses a matrix strategy for 4 targets: windows-latest (win-x64) and
  ubuntu-latest (linux-x64) and macos-latest (osx-x64) and macos-latest with ARM (osx-arm64)'
- Each matrix leg runs cargo fmt --check and cargo clippy -- -D warnings and cargo
  test (native only) and cargo build --release
- Native binaries uploaded as GitHub Actions artifacts per target
- 'dotnet-build job depends on rust-build: downloads all 4 artifacts and runs dotnet
  build and dotnet test and dotnet pack'
- Full pipeline completes in under 15 minutes
created: '2026-03-26'
epic_id: EPIC-WNE-9
id: US-WNE-48
points: 5
priority: must
status: done
tags:
- ci
- github-actions
- pipeline
title: GitHub Actions CI pipeline
updated: '2026-03-29'
---

As a maintainer, I want a GitHub Actions CI pipeline that builds all native targets and the .NET package on every push and PR so that regressions are caught automatically.