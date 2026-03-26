---
created: '2026-03-26'
id: EPIC-WNE-7
points: null
priority: must
status: draft
tags:
- csharp
- testing
- mvp
target_date: null
title: C# Unit Tests
updated: '2026-03-26'
---

Comprehensive C# xUnit test suite. Test P/Invoke marshalling correctness, Socket API surface (all method signatures match expected behavior), WgDevice lifecycle (create/dispose ordering, double-dispose safety, finalizer fallback), WgConfig/WgPeer model validation, error code to exception mapping, and NetworkStream wrapper behavior. Mock the native layer where needed for pure-unit isolation.