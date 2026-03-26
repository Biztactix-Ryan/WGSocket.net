---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-61-7
id: US-WNE-61-8
points: 1
status: todo
story_id: US-WNE-61
tags: []
title: Add code examples to doc comments for API reference
updated: '2026-03-26'
---

Enhance existing XML doc comments with example elements that render well in docfx output. Add usage examples to Socket (listen/connect patterns), WgDevice (setup and teardown), WgConfig (loading from file), WgPeer (adding peers), and NetworkStream (async read/write). Add see-cref cross-references between related types so docfx generates clickable links.