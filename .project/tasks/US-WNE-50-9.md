---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-50-9
points: 1
status: todo
story_id: US-WNE-50
tags: []
title: Add .NET runtime native library resolution
updated: '2026-03-26'
---

Ensure the .NET runtime can locate the native library at runtime using NativeLibrary.SetDllImportResolver or by relying on the default RID-based probing. If needed, create a NativeLibraryLoader static constructor that registers a custom resolver. Verify DllImport or LibraryImport attributes reference the correct library name (wgsocket_native without lib prefix or extension).