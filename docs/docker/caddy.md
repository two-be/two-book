---
tags:
  - Caddy
  - Docker
---

## docker-compose.yml
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

## Caddyfile
```conf
localhost {
    reverse_proxy 127.0.0.1:9005
}
```