---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-9-8
points: 1
status: todo
story_id: US-WNE-9
tags: []
title: Verify AOT source generator compilation
updated: '2026-03-26'
---

Ensure the NativeMethods partial class compiles cleanly with the .NET 8 LibraryImport source generator. Run dotnet build with PublishAot=true in a test project. Fix any generator warnings (SYSLIB1054, SYSLIB1051). Confirm no legacy DllImport attributes remain via a code search. Add an analyzer rule or EditorConfig entry to flag DllImport usage.