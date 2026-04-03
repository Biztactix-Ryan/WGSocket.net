---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-53-8
points: 1
status: done
story_id: US-WNE-53
tags: []
title: Add version synchronization between .csproj and Cargo.toml
updated: '2026-04-03'
---

Create a script or CI step that extracts the version from Cargo.toml and compares it to the Version property in WgSocket.csproj. If they differ, fail with a clear message. Optionally, use the Cargo.toml version as the single source of truth by having MSBuild read it (via a targets file or pre-build script that sets the version).