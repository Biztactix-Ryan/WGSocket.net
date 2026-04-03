---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-45-7
id: US-WNE-45-8
points: 1
status: done
story_id: US-WNE-45
tags: []
title: Set up runtimes/{rid}/native/ output directory mapping
updated: '2026-03-29'
---

Configure the build script to copy compiled native binaries into the correct NuGet RID directory structure: runtimes/win-x64/native/wgsocket_native.dll, runtimes/linux-x64/native/libwgsocket_native.so, runtimes/osx-x64/native/libwgsocket_native.dylib, runtimes/osx-arm64/native/libwgsocket_native.dylib. Handle platform-specific library naming conventions (lib prefix, .dll/.so/.dylib extensions).