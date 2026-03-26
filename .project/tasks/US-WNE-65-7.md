---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-65-7
points: 1
status: todo
story_id: US-WNE-65
tags: []
title: Configure Dependabot for Cargo.toml and .csproj
updated: '2026-03-26'
---

Create .github/dependabot.yml with package ecosystems for both cargo and nuget. Set update schedule to weekly. Configure native/cargo Dependabot PRs with a 'manual-review-required' label and auto-merge disabled. NuGet PRs can use default auto-merge policy. Add CODEOWNERS entry requiring security team review for Cargo.lock changes.