---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-65-6
- US-WNE-65-8
id: US-WNE-65-9
points: 1
status: todo
story_id: US-WNE-65
tags: []
title: 'Test: verify CI workflows catch known vulnerabilities'
updated: '2026-03-26'
---

Validate the CI integration by temporarily adding a known-vulnerable crate version to a test branch and confirming cargo audit fails the workflow. Similarly test dotnet vulnerability scanning with a known-vulnerable NuGet package. Document the test procedure for future validation.