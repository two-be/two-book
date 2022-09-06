---
tags:
  - docker
  - postgres
---

## docker-compose.yml
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