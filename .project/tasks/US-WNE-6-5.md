---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-6-5
points: 1
status: todo
story_id: US-WNE-6
tags: []
title: Implement ConfigBuilder struct
updated: '2026-03-26'
---

Create ConfigBuilder in config.rs with a fluent API. Methods: ConfigBuilder::new() -> Self, .private_key(key: &[u8; 32]) -> Self, .listen_port(port: u16) -> Self, .address(addr: IpNet) -> Self, .dns(dns: IpAddr) -> Self. Store intermediate state in Option fields. Each setter consumes and returns self for chaining.