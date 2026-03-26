---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-48-7
- US-WNE-48-8
- US-WNE-48-9
- US-WNE-48-10
- US-WNE-48-11
id: US-WNE-48-12
points: 2
status: todo
story_id: US-WNE-48
tags: []
title: Validate CI pipeline end-to-end
updated: '2026-03-26'
---

Push the workflow to a branch, open a PR, and verify: (1) all 4 rust-build matrix legs pass, (2) dotnet-build job triggers after rust-build, (3) dotnet test passes, (4) .nupkg artifact is produced, (5) total pipeline time is under 15 minutes. Fix any path or artifact naming issues discovered during the dry run.