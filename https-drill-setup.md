---
layout: page
title: Https Setup
permalink: /https-drill-setup/
---

If your application uses **https** for access you need to deploy additional **ssl-proxy** service
to Drill admin setup:
```yaml
ssl-proxy-admin:
    image: drill4j/ssl-proxy:latest
    ports:
      - 8443:8443
    environment:
      DOMAIN: drill4j.example.com
      SSL_PORT: 8443
      TARGET_HOST: admin-ui
      TARGET_PORT: 8080
```

For example, full docker-compose file looks like:
```yaml
version: '3'

services:
ssl-proxy-admin:
    image: drill4j/ssl-proxy:latest
    ports:
      - 8443:8443
    environment:
      DOMAIN: drill4j.example.com
      SSL_PORT: 8443
      TARGET_HOST: admin-ui
      TARGET_PORT: 8080
    networks:
          - drill4j-dev-network

  drill-admin:
    image: drill4j/admin:0.6.0
    environment:
      - TEST2CODE_PLUGIN_VERSION=0.6.0
      - LOG_LEVEL=INFO
    ports:
      - 8090:8090
    networks:
      - drill4j-dev-network

  admin-ui:
    image: drill4j/admin-ui:0.6.0
    ports:
      - 8091:8080
    networks:
      - drill4j-dev-network

networks:
  drill4j-dev-network:
```
After that Drill admin is available on **https://drillAdminHost:8443**
> Accept self signed certificate
