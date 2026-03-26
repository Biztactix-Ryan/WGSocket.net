---
assignee: null
created: '2026-03-26'
depends_on:
- US-WNE-33-9
id: US-WNE-33-12
points: 1
status: todo
story_id: US-WNE-33
tags: []
title: Implement ToString redaction and builder pattern tests
updated: '2026-03-26'
---

Write tests asserting that WgConfig.ToString() and WgPeer.ToString() never include raw private key or PSK material in their output -- the output should contain a redaction marker like '[REDACTED]' or omit the field entirely. Also test that the builder/initializer pattern (if using a fluent builder) produces equivalent objects to direct construction and that incomplete builders throw on Build().