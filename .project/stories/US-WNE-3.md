---
acceptance_criteria:
- Parses [Interface] section including PrivateKey ListenPort Address and DNS fields
- Parses [Peer] sections including PublicKey Endpoint AllowedIPs PresharedKey and
  PersistentKeepalive fields
- Handles multiple [Peer] sections in a single config file
- Ignores comments (# lines) and blank lines
- Returns descriptive error messages for malformed input including line numbers
created: '2026-03-26'
epic_id: EPIC-WNE-2
id: US-WNE-3
points: 3
priority: must
status: done
tags:
- rust
- config
- parser
- mvp
title: wg.conf file parser
updated: '2026-03-26'
---

As a developer, I want to parse standard wg.conf files so that users can reuse existing WireGuard configurations.