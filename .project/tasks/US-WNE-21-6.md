---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-21-6
points: 2
status: todo
story_id: US-WNE-21
tags: []
title: Create cbindgen.toml and build.rs integration
updated: '2026-03-26'
---

Add cbindgen as a build dependency in Cargo.toml. Create cbindgen.toml with: language = "C", include_guard = "WGSOCKET_H", autogen warning comment, sys_includes for stdint.h and stdbool.h, proper style = "both" for tagged enums. Create or update build.rs to invoke cbindgen::generate() targeting include/wgsocket.h. Ensure all #[no_mangle] extern "C" functions, error constants, and repr(C) structs (WgConfig, WgStats) appear in the generated header.