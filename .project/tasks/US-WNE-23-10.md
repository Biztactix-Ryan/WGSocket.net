---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-23-10
points: 2
status: done
story_id: US-WNE-23
tags: []
title: Create config test fixtures and helper module
updated: '2026-03-27'
---

Create a tests/config_fixtures.rs module with: valid single-peer wg.conf string, valid multi-peer wg.conf string, configs exercising all optional fields (PresharedKey, PersistentKeepalive, DNS), and helper functions to generate malformed configs (bad base64, bad CIDR, bad endpoints, missing fields). Also include configs with comments, blank lines, and mixed whitespace. This module is the foundation for all config parsing tests.