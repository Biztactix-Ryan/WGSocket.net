---
assignee: claude
created: '2026-03-26'
depends_on:
- US-WNE-3-6
id: US-WNE-3-7
points: 1
status: done
story_id: US-WNE-3
tags: []
title: Implement Interface section parser
updated: '2026-03-26'
---

Parse the [Interface] section tokens into WgConfig fields. Map PrivateKey to base64-decoded [u8; 32], ListenPort to u16, Address to Vec<IpNet> (comma-separated CIDR values), DNS to Vec<IpAddr> (comma-separated). Return ConfigError::ParseError with line number for unrecognized keys or malformed values. Handle the case where [Interface] is missing entirely.