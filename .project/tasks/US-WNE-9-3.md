---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-9-8
id: US-WNE-9-3
points: 1
status: todo
story_id: US-WNE-9
tags: []
title: 'Test: AOT source generator produces no warnings'
updated: '2026-03-26'
---

Create a test that builds the interop project with PublishAot=true and verifies zero SYSLIB1054/SYSLIB1051 warnings. Can be an integration test or MSBuild target that fails the build on source generator diagnostics. Verify the generated marshalling code exists in the obj directory.