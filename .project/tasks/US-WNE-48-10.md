---
assignee: null
created: '2026-03-26'
depends_on: []
id: US-WNE-48-10
points: 2
status: todo
story_id: US-WNE-48
tags: []
title: Create dotnet-build CI job with artifact download
updated: '2026-03-26'
---

Add a dotnet-build job that needs: [rust-build]. Use actions/download-artifact@v4 to download all 4 native artifacts. Place each binary into the correct runtimes/{rid}/native/ path relative to the WgSocket.csproj. Install .NET 8 SDK via actions/setup-dotnet@v4. Run dotnet restore, dotnet build --no-restore, dotnet test --no-build.