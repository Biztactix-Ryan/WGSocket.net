---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-52-6
points: 1
status: todo
story_id: US-WNE-52
tags: []
title: Create cbindgen.toml and generate baseline header
updated: '2026-03-26'
---

Create cbindgen.toml in src/wgsocket-native/ with: language = "C", include_guard = "WGSOCKET_H", appropriate style settings, and header/trailer comments noting the file is auto-generated. Run cbindgen --config cbindgen.toml --crate wgsocket-native --output include/wgsocket.h to generate the baseline header. Check in both cbindgen.toml and the generated header.