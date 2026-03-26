---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-2-7
points: 1
status: todo
story_id: US-WNE-2
tags: []
title: Define ConfigError enum
updated: '2026-03-26'
---

Create a ConfigError enum in config.rs with variants for all error conditions: InvalidKey(String), InvalidCidr(String), InvalidEndpoint(String), MissingField(String), ParseError { line: usize, message: String }, ValidationError(String). Implement std::fmt::Display and std::error::Error for the enum. Ensure error messages are descriptive and actionable.