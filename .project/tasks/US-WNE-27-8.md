---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-27-8
points: 2
status: done
story_id: US-WNE-27
tags: []
title: Create smoltcp test harness with loopback interface
updated: '2026-03-27'
---

Build a test harness module that creates a smoltcp Interface with a loopback-style virtual device, configures it with an IP address (e.g. 10.0.0.1/24), and provides helpers: create_interface() returning (Interface, Device), poll_until_ready(iface, timeout) that polls the interface until a socket event or timeout, and socket allocation helpers for TCP and UDP. This harness underpins all smoltcp socket tests.