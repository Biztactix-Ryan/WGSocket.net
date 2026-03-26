---
created: '2026-03-26'
id: EPIC-WNE-9
points: null
priority: should
status: draft
tags:
- ci
- packaging
- devops
target_date: null
title: Build, CI/CD & NuGet Packaging
updated: '2026-03-26'
---

Set up the solution structure (WgSocket.sln), project files, cross-compilation for 4 targets (win-x64, linux-x64, osx-x64, osx-arm64), GitHub Actions pipeline (rust-build matrix → dotnet-build → dotnet pack), NuGet .nupkg with embedded native binaries in runtimes/{rid}/native/, cbindgen staleness check in CI, and publish workflow (manual trigger or git tag). The NuGet package must be self-contained — `dotnet add package WgSocket` is the only step for consumers.