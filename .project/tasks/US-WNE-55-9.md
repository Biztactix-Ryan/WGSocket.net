---
assignee: claude
created: '2026-03-26'
depends_on: []
id: US-WNE-55-9
points: 1
status: done
story_id: US-WNE-55
tags: []
title: Scaffold EchoServer console app project
updated: '2026-04-03'
---

Create samples/EchoServer/ directory with a .csproj that targets net8.0 and references the WgSocket project. Add Program.cs with a minimal Main entry point. The .csproj should use ProjectReference to the main WgSocket library. Ensure the project builds successfully as part of the solution.