---
acceptance_criteria:
- WgSocket.sln at repo root with all projects referenced
- src/WgSocket/WgSocket.csproj targeting net8.0 with proper SDK-style format
- src/WgSocket.Tests/WgSocket.Tests.csproj with xUnit and Microsoft.NET.Test.Sdk references
- src/wgsocket-native/Cargo.toml configured as cdylib crate type
- dotnet build succeeds locally without errors
- dotnet test runs and passes locally
- Local dev references native library via local path convention
created: '2026-03-26'
epic_id: EPIC-WNE-9
id: US-WNE-42
points: 2
priority: must
status: backlog
tags:
- ci
- structure
- mvp
title: Solution & project structure setup
updated: '2026-03-26'
---

As a developer, I want the .NET solution and Rust crate project structure properly configured so that I can build and test locally with a single command.