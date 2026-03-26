---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-13-5
points: 2
status: todo
story_id: US-WNE-13
tags: []
title: Implement NativeLibrary.SetDllImportResolver for wgsocket
updated: '2026-03-26'
---

Register a custom DllImportResolver in a module initializer or static constructor that resolves "wgsocket" by probing runtimes/{rid}/native/ relative to the assembly location. Use RuntimeInformation.RuntimeIdentifier to determine the correct subdirectory. Probe order: exact RID, then fallback (e.g., linux-x64 for linux-musl-x64). Return IntPtr.Zero to fall back to default resolution if custom probing fails.