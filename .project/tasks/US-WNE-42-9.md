---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-42-9
points: 1
status: done
story_id: US-WNE-42
tags: []
title: Create src/WgSocket.Tests/WgSocket.Tests.csproj with xUnit
updated: '2026-03-28'
---

Create test project at src/WgSocket.Tests/WgSocket.Tests.csproj. Reference xUnit, xunit.runner.visualstudio, Microsoft.NET.Test.Sdk, coverlet.collector. Add ProjectReference to WgSocket.csproj. Include a placeholder test that asserts true so dotnet test passes.