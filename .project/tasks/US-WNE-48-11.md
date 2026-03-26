---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-48-11
points: 1
status: todo
story_id: US-WNE-48
tags: []
title: Add dotnet pack step to CI
updated: '2026-03-26'
---

After dotnet test passes, run dotnet pack --configuration Release --no-build --output ./artifacts. Upload the .nupkg as a CI artifact using actions/upload-artifact@v4 named nuget-package. This artifact is used by the publish workflow and is available for manual download on PR builds.