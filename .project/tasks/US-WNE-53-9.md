---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-53-9
points: 1
status: todo
story_id: US-WNE-53
tags: []
title: Add NuGet push and GitHub release steps
updated: '2026-03-26'
---

In the publish workflow, after dotnet pack: (1) push .nupkg to nuget.org via dotnet nuget push using the NUGET_API_KEY repository secret, (2) create a GitHub release using softprops/action-gh-release@v2 or gh CLI with the tag name as the release title, auto-generated changelog (--generate-notes), and the .nupkg attached as a release asset.