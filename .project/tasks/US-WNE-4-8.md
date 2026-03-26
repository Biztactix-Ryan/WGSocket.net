---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-4-8
points: 2
status: todo
story_id: US-WNE-4
tags: []
title: Implement full config validation pass
updated: '2026-03-26'
---

Create WgConfig::validate(&self) -> Result<(), Vec<ConfigError>> that runs all validators: checks private_key is present and valid, checks listen_port in 1-65535 if set, validates all peer public_keys, validates all peer preshared_keys if present, validates all AllowedIPs entries, validates all endpoints, checks at least one peer exists. Collect ALL errors (do not short-circuit) so users see every problem at once.