# own-trello
Setup own service like Trello inside your local network

## Why?
New times force us to bring up our own services on our private local network.

# Synology setup

### KanBoard (with SQLite3)
`compose.yml`
```YML
version: '3'
services:
  kanboard:
    image: kanboard/kanboard:v1.2.36
    container_name: kanboard
    restart: always
    volumes:
      - /volume1/docker/kanboard/data:/var/www/app/data
      - /volume1/docker/kanboard/plugins:/var/www/app/plugins
      - /volume1/docker/kanboard/ssl:/etc/nginx/ssl
    ports:
      # - "80:80"
      - "3005:443"
```
