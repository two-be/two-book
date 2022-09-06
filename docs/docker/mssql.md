---
tags:
  - Docker
  - mssql
  - Sql Server
---

## docker-compose.yml
```yaml
version: "x.x"

services:

  mssql:
    image: "mcr.microsoft.com/mssql/server:2022-latest"
    environment:
      ACCEPT_EULA: "Y"
      # MSSQL_PID: "Express"
      SA_PASSWORD: "password"
    ports:
      - "1433:1433"
    volumes:
      - "./mssql/data:/var/opt/mssql/data"
      - "./mssql/log:/var/opt/mssql/log"
      - "./mssql/secrets:/var/opt/mssql/secrets"
```