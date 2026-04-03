---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-48-7
id: US-WNE-48-9
points: 1
status: done
story_id: US-WNE-48
tags: []
title: Upload native binaries as CI artifacts
updated: '2026-03-29'
---

After cargo build --release, use actions/upload-artifact@v4 to upload the compiled native binary. Name each artifact by RID (e.g., native-win-x64). Map the correct binary path per target: target/{triple}/release/wgsocket_native.dll (Windows), libwgsocket_native.so (Linux), libwgsocket_native.dylib (macOS). Each artifact should contain just the binary file.