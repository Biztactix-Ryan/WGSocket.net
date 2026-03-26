---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-1-6
points: 1
status: todo
story_id: US-WNE-1
tags: []
title: Add boringtun and smoltcp dependencies with feature flags
updated: '2026-03-26'
---

Add boringtun (WireGuard crypto) and smoltcp (userspace TCP/IP stack) as dependencies in Cargo.toml. Pin compatible versions. Configure smoltcp feature flags: enable socket-tcp, socket-udp, medium-ip, proto-ipv4, proto-ipv6. Add log and env_logger for debug builds. Ensure cargo build completes without errors.