---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-42-8
points: 1
status: todo
story_id: US-WNE-42
tags: []
title: Create WgSocket.sln and src/WgSocket/WgSocket.csproj
updated: '2026-03-26'
---

Create the solution file at repo root. Add src/WgSocket/WgSocket.csproj as an SDK-style project targeting net8.0. Include PropertyGroup with RootNamespace, AssemblyName, LangVersion=latest, Nullable=enable, ImplicitUsings=enable. Add a placeholder Class1.cs so the project compiles.