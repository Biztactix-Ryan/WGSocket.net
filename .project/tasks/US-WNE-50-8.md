---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-50-8
points: 2
status: done
story_id: US-WNE-50
tags: []
title: Configure runtimes/{rid}/native/ MSBuild items
updated: '2026-03-29'
---

Add Content or None items in .csproj for each native binary: runtimes/win-x64/native/wgsocket_native.dll, runtimes/linux-x64/native/libwgsocket_native.so, runtimes/osx-x64/native/libwgsocket_native.dylib, runtimes/osx-arm64/native/libwgsocket_native.dylib. Set PackagePath=runtimes/{rid}/native/, Pack=true, CopyToOutputDirectory=PreserveNewest. Use Condition to handle missing files during local dev gracefully.