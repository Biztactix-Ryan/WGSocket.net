---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-65-8
points: 1
status: todo
story_id: US-WNE-65
tags: []
title: Add dotnet vulnerability scanning to CI
updated: '2026-03-26'
---

Add a step to the existing CI workflow (or create a new one) that runs `dotnet list package --vulnerable --include-transitive` and fails the build if any known vulnerable packages are found. Run on PR and weekly schedule alongside cargo audit.