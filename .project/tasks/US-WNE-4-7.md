---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-4-7
points: 2
status: done
story_id: US-WNE-4
tags: []
title: Implement CIDR and endpoint validation
updated: '2026-03-26'
---

Create validate_cidr(cidr_str: &str) -> Result<IpNet, ConfigError> that parses and validates CIDR notation (e.g. 10.0.0.0/24, fd00::1/128), rejecting invalid prefixes and out-of-range masks. Create validate_endpoint(endpoint_str: &str) -> Result<Endpoint, ConfigError> that accepts IP:port (both IPv4 and IPv6 with bracket notation) and hostname:port, validating port range 1-65535. Define an Endpoint enum or struct to represent the parsed result.