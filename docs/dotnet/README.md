---
tags:
  - .NET
  - dotnet
---

## Trims unused libraries to reduce the deployment size of an app when publishing a self-contained executable.

```
dotnet publish ~/projects/app/app.csproj -c Release -o published -p:PublishTrimmed=true -r linux-x64
```