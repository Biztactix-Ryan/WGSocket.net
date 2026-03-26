---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-37-7
points: 2
status: todo
story_id: US-WNE-37
tags: []
title: Create INativeMethodsProxy interface and mock for P/Invoke testing
updated: '2026-03-26'
---

Define an INativeMethodsProxy interface mirroring all NativeMethods P/Invoke declarations. Implement a MockNativeMethodsProxy using Moq or manual fakes that returns configurable return codes and populates output buffers. This enables testing the marshalling layer without the native Rust library loaded. Register the interface in test DI or pass it directly to the classes under test.