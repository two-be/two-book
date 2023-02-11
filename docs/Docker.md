---
tags:
  - Docker
---

## depends_on
```yaml
  depends_on:
    - "db"
```

## Start containers automatically
```yaml
  restart: "always"
```

## timezone
```yaml
  environment:
    TZ: "Asia/Bangkok"
```

## docker-compose.yml
=== "ASP.NET"
    ```yaml
    version: "x.x"

    services:

      app:
        image: "aspnetapp"
        volumes:
          - "./appsettings.json:/app/appsettings.json"
    ```

    *Dockerfile*
    ```dockerfile
    FROM mcr.microsoft.com/dotnet/aspnet:x.x
    WORKDIR /app
    COPY  /published ./
    ENTRYPOINT ["dotnet", "aspnetapp.dll"]
    ```

=== "Caddy"

    ```yaml
    version: "x.x"

    services:

      caddy:
        image: "caddy"
        ports:
          - "80:80"
          - "443:443"
        volumes:
          - "./Caddyfile:/etc/caddy/Caddyfile"
          - "caddy_data:/data"

    volumes:
      caddy_data:
    ```

    *Caddyfile*
    ```conf
    localhost {
        reverse_proxy 127.0.0.1:9005
    }
    ```

=== "Microsoft SQL Server"

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

=== "PostgreSQL"

    ```yaml
    version: "x.x"

    services:

      postgres:
        image: "postgres"
        environment:
          POSTGRES_PASSWORD: "password"
          POSTGRES_USER: "postgres"
        ports:
          - "5432:5432"
        volumes:
          - "./postgresql/data:/var/lib/postgresql/data"
    ```