---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-13-5
id: US-WNE-13-1
points: 1
status: todo
story_id: US-WNE-13
tags: []
title: 'Test: Library resolves from runtimes/{rid}/native/ path'
updated: '2026-03-26'
---

Test that the custom DllImportResolver probes the correct runtimes/{rid}/native/ path based on RuntimeInformation.RuntimeIdentifier. Mock the file system or NativeLibrary.TryLoad to verify the expected paths are probed in order. Verify the resolver returns a valid handle when the library exists at the expected path.