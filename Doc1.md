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
    accTitle: the architecture
    accDescr: a architecture graph with four nodes
  group aws-services(aws:aws)[AWS Services] {
    service lambda(aws:aws-lambda)[Lambda]
    service s3(aws:amazon-simple-storage-service)[S3]
    service ec2(aws:aws-ec2)[EC2]
    service rds(aws:amazon-rds)[RDS]
  }

    service db(database)[Database] in api
    service disk1(disk)[Storage] in api
    service disk2(disk)[Storage] in api
    service server(server)[Server] in api

    db:L -- R:server
    disk1:T -- B:server
    disk2:T -- B:db
```
```mermaid
flowchart TB

subgraph ACCOUNT[AWS Account]
  subgraph GRP1[" "]
    ELB@{ img: "https://api.iconify.design/logos/aws-elb.svg", label: "ELB", pos: "b", w: 60, h: 60, constraint: "on" }
  end
  subgraph GRP2[" "]
    EC2@{ img: "https://api.iconify.design/logos/aws-ec2.svg", label: "EC2", pos: "b", w: 60, h: 60, constraint: "on" }
  end
  subgraph GRP3[" "]
    RDS@{ img: "https://api.iconify.design/logos/aws-rds.svg", label: "RDS", pos: "b", w: 60, h: 60, constraint: "on" }
  end
  ELB --- EC2 --- RDS
end

classDef vpc fill:none,color:#0a0,stroke:#0a0
class ACCOUNT vpc

classDef group fill:none,stroke:none
class GRP1,GRP2,GRP3 group
```
