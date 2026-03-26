---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-3-9
points: 1
status: todo
story_id: US-WNE-3
tags: []
title: Implement WgConfig::from_str and from_file
updated: '2026-03-26'
---

Implement std::str::FromStr for WgConfig that orchestrates tokenization, Interface parsing, and Peer parsing. Add a WgConfig::from_file(path: &Path) -> Result<WgConfig, ConfigError> convenience method that reads the file and delegates to FromStr. Ensure the full pipeline produces clear, chained error messages.