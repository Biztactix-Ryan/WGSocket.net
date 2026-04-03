---
created: '2026-03-26'
id: EPIC-WNE-4
points: null
priority: must
status: done
tags:
- csharp
- interop
- mvp
target_date: null
title: C# Interop Layer
updated: '2026-03-27'
---

Build the C# P/Invoke interop layer in NativeMethods.cs using LibraryImport (source-generated, AOT-compatible). Map all C ABI functions to managed signatures. Implement safe handle wrappers (SafeHandle subclasses), error code to exception mapping, and Span-based buffer marshalling. This layer isolates all unsafe/native concerns from the public API.