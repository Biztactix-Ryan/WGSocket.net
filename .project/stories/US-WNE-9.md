---
acceptance_criteria:
- All FFI functions declared with [LibraryImport("wgsocket")]
- Correct marshalling attributes for string and pointer and buffer parameters
- Compiles with .NET 8 source generator
- No legacy DllImport usage anywhere in codebase
created: '2026-03-26'
epic_id: EPIC-WNE-4
id: US-WNE-9
points: 3
priority: must
status: backlog
tags:
- interop
- pinvoke
- aot
- mvp
title: LibraryImport P/Invoke declarations
updated: '2026-03-26'
---

As a library developer, I want all FFI functions from wgsocket.h declared as LibraryImport P/Invoke methods in NativeMethods.cs so that the interop layer is AOT-compatible and uses .NET 8 source-generated marshalling.