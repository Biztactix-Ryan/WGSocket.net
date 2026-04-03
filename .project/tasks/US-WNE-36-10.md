---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-36-10
points: 2
status: done
story_id: US-WNE-36
tags: []
title: Implement xUnit collection fixture and CI port allocation
updated: '2026-03-28'
---

Create an xUnit IAsyncLifetime collection fixture (WgIntegrationFixture) that manages shared state across integration test classes. Implement a thread-safe port allocator that avoids port conflicts when tests run in parallel. Add [Trait] attributes for filtering integration tests. Ensure the fixture detects CI environment and adjusts timeouts accordingly.