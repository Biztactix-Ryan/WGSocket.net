---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-54-6
points: 1
status: todo
story_id: US-WNE-54
tags: []
title: Scaffold ExceptionMappingTests with error code table
updated: '2026-03-26'
---

Create ExceptionMappingTests.cs with a comprehensive table mapping every known native error code to its expected managed exception type. Include test data for: success (0), invalid config, device creation failure, socket error, permission denied, tunnel down, and any other defined codes. Set up parameterized test infrastructure using xUnit Theory/InlineData.