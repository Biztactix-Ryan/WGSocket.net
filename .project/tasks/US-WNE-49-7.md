---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-49-7
points: 3
status: done
story_id: US-WNE-49
tags: []
title: Implement wireguard-go process manager for interop tests
updated: '2026-04-03'
---

Create a WireguardGoProcess helper that: detects if wireguard-go is available on PATH or in a known CI location, starts a wireguard-go process with generated config (private key, listen port, peer config), waits for the interface to be ready, and provides cleanup on disposal. Returns skip reason if wireguard-go is not available. Handles platform differences (Linux vs macOS).