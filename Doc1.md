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

    service server(server)[App Server] in api
    service db(database)[MariaDB] in api
    service server(server)[Video Cam] in api
    service server(server)[Video Cam] in api
    service server(server)[Video Cam] in api

    db:L -- R:server
    disk1:T -- B:server
    disk2:T -- B:db
```
