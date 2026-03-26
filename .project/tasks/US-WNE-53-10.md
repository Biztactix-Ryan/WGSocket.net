---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-53-7
- US-WNE-53-8
- US-WNE-53-9
id: US-WNE-53-10
points: 1
status: todo
story_id: US-WNE-53
tags: []
title: Validate publish workflow with dry run
updated: '2026-03-26'
---

Test the publish workflow via manual dispatch on a non-main branch with a dry-run flag (skip the actual nuget push). Verify: workflow triggers correctly, all build steps pass, .nupkg is produced, version matches between .csproj and Cargo.toml, GitHub release step would execute. Confirm the workflow does a full fresh build (not using cached artifacts from CI).