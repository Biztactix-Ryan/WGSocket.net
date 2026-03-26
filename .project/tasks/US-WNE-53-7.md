---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-53-7
points: 2
status: todo
story_id: US-WNE-53
tags: []
title: Create publish workflow YAML
updated: '2026-03-26'
---

Create .github/workflows/publish.yml triggered on workflow_dispatch and push tags matching 'v*'. The workflow should: (1) check out code, (2) run the full rust-build matrix (reuse the CI workflow logic or use a reusable workflow), (3) run dotnet build and dotnet pack with Release configuration, (4) upload .nupkg as artifact. Use environment: nuget for deployment protection if desired.