---
nav_order: Home
layout: default
title: Graphic
nav_enabled: true
---

```mermaid
graph TD;
    accTitle: the diamond pattern
    accDescr: a graph with four nodes: A points to B and C, while B and C both point to D
    A-->B;
    A-->C;
    B-->D;
    C-->D;
```
```mermaid
architecture-beta
    group api(cloud)[Comm GW]

    service app_server(server)[App Server] in api
    service db(database)[MariaDB] in api
    service server1(server)[Video Cam] in api
    service server2(server)[Video Cam] in api
    service server3(server)[Video Cam] in api

    db:L -- R:app_server
    server1:T -- B:app_server
    server2:T -- B:app_server
    server3:T -- B:app_server
```
