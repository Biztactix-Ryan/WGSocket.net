---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-4-6
points: 1
status: todo
story_id: US-WNE-4
tags: []
title: Implement key validation (base64 + length)
updated: '2026-03-26'
---

Create a validate_key(base64_str: &str, field_name: &str) -> Result<[u8; 32], ConfigError> function that: decodes the base64 string, checks decoded length is exactly 32 bytes (Curve25519 key size), returns ConfigError::InvalidKey with field name and reason on failure. Also create validate_key_bytes(bytes: &[u8], field_name: &str) for raw byte validation (length check only). Handle standard base64 and base64 with padding.