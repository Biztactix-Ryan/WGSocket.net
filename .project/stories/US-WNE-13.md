---
acceptance_criteria:
- Library resolves correctly from runtimes/{rid}/native/ in NuGet package
- DllNotFoundException provides helpful message about missing native binary for current
  platform
- Works on win-x64 and linux-x64 and osx-x64 and osx-arm64
- Custom NativeLibrary.SetDllImportResolver if needed for non-standard paths
created: '2026-03-26'
epic_id: EPIC-WNE-4
id: US-WNE-13
points: 2
priority: must
status: done
tags:
- interop
- nuget
- platform
- mvp
title: Native library loading and platform resolution
updated: '2026-03-26'
---

As a library consumer, I want the native wgsocket library to resolve automatically from the NuGet package on all supported platforms so that I do not need manual native binary setup.