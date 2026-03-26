---
acceptance_criteria:
- Workflow triggers on manual dispatch (workflow_dispatch) or git tag matching v*
  pattern
- Builds fresh from source (not from cached artifacts) to ensure reproducibility
- Pushes .nupkg to nuget.org using NUGET_API_KEY secret
- Version in .csproj matches Cargo.toml version (single source of truth)
- GitHub release created automatically with tag name and changelog
- Release includes the .nupkg as a downloadable asset
created: '2026-03-26'
epic_id: EPIC-WNE-9
id: US-WNE-53
points: 2
priority: should
status: backlog
tags:
- ci
- release
- nuget
title: Release & publish workflow
updated: '2026-03-26'
---

As a maintainer, I want an automated release workflow that publishes the NuGet package and creates a GitHub release so that shipping a new version is a single-step process.