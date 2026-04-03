---
created: '2026-03-26'
id: EPIC-WNE-2
points: null
priority: must
status: done
tags:
- rust
- config
- mvp
target_date: null
title: WireGuard Configuration
updated: '2026-03-26'
---

Implement WireGuard configuration parsing and validation. Support both wg.conf file format parsing (config.rs) and a programmatic Rust API for building configs. Validate keys, endpoints, AllowedIPs, and listen port. This feeds into both the Rust device initialization and the C# WgConfig model.