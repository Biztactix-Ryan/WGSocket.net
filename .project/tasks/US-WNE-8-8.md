---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-8-8
points: 1
status: todo
story_id: US-WNE-8
tags: []
title: Implement IP address and route configuration from AllowedIPs
updated: '2026-03-26'
---

Parse WireGuard AllowedIPs CIDR notation (e.g. 10.0.0.1/24, fd00::1/128) into smoltcp IpCidr entries. Set the interface IP address from the tunnel address. Add routing table entries: AllowedIPs subnets route through the virtual device. Support both IPv4 and IPv6 addresses. Validate that configured IPs don't conflict.