---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-50-7
- US-WNE-50-8
- US-WNE-50-9
id: US-WNE-50-10
points: 2
status: done
story_id: US-WNE-50
tags: []
title: Validate NuGet package contents and consumer install
updated: '2026-03-29'
---

Run dotnet pack and inspect the .nupkg (it is a ZIP file) to verify: all 4 native binaries are present under runtimes/{rid}/native/, package metadata is correct, package size is 8-16MB. Create a temporary .NET 8 console project, add the local .nupkg as a source, install it, write a trivial P/Invoke call, and verify the native library loads without errors.