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
flowchart BT
 subgraph mediaServers["Media Content Servers"]
        media1["📹 Media Server 1"]
        media2["📹 Media Server 2"]
        media3["📹 Media Server 3"]
  end
 subgraph appServer["⚙️ Application Server"]
        server1["Motion"]
        database["MariaDB"]
        server2["NGNIX"]
  end
 subgraph vpc["AWS VPC"]
    direction BT
        igw["🌐 Gateway"]
        appServer
        mediaServers
  end
    igw -- Traffic <--> internet["External Communicatoins"]
    appServer -- Route --> igw
    media1 -- Distribute --> appServer
    media2 -- Distribute --> appServer
    media3 -- Distribute --> appServer

     media1:::mediaStyle
     media1:::mediaStyle
     media2:::mediaStyle
     media2:::mediaStyle
     media3:::mediaStyle
     media3:::mediaStyle
     igw:::gatewayStyle
     appServer:::appStyle
     internet:::internetStyle
    classDef vpcStyle stroke:#2dd4bf,fill:#f0fdfa
    classDef gatewayStyle stroke:#38bdf8,fill:#f0f9ff
    classDef appStyle stroke:#818cf8,fill:#eef2ff
    classDef mediaStyle stroke:#fb923c,fill:#fff7ed
    classDef internetStyle stroke:#f87171,fill:#fef2f2
```
