---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-42-10
points: 1
status: done
story_id: US-WNE-42
tags: []
title: Configure src/wgsocket-native/Cargo.toml as cdylib
updated: '2026-03-28'
---

Ensure Cargo.toml in src/wgsocket-native/ has [lib] crate-type = ["cdylib"]. Verify the crate name is wgsocket_native. Add a minimal #[no_mangle] pub extern "C" fn placeholder so cargo build produces a shared library. Add cbindgen as a build dependency if not already present.