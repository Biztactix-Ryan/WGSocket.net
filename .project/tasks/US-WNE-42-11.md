---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-42-11
points: 1
status: todo
story_id: US-WNE-42
tags: []
title: Configure local native library path for dev builds
updated: '2026-03-26'
---

Set up the .csproj or a Directory.Build.props so that local dev builds can find the native library from cargo's target/release/ output directory. Use a conditional MSBuild property (e.g. WgSocketNativeDir) that defaults to the local cargo output path. Document the local build workflow in a comment or README section.