---
tags:
  - .NET
  - docker
  - dotnet
---

## docker-compose.yml
```yaml
version: "x.x"

services:

  app:
    image: "aspnetapp"
    volumes:
      - "./appsettings.json:/app/appsettings.json"
```

## Dockerfile
```dockerfile
FROM mcr.microsoft.com/dotnet/aspnet:x.x
WORKDIR /app
COPY  ./published ./
ENTRYPOINT ["dotnet", "aspnetapp.dll"]
```