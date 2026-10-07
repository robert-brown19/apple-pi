---
nav_order: Home
layout: default
title: Home1
nav_enabled: true
---

## Securing a Raspberry Pi to Military Standards ##

Project Requirements:  
    1. Follow a simplified Acquisition and Systems Engineering Process  
    2. https://www.linkedin.com/pulse/cybersecurity-process-integration-v-model-development-jadhav-dvnpc/  
    3. Focus on Cybersecurity and not the Platform.  The platform is tailored for specific Cybersecurity use cases.  
    4. The platform is to be a real-world platform not a rock sitting in a safe.  
    
### Instantiated requirements ###

#### Hardware: ####

Video  Camera
:  Video is easily implemented on the entire suite of Raspberry Pi products.  It is in effect a sensor.  It could be substituted with a microphone, a temperature sensor, etc.  

Edge architecture  
: Communications are always a key architecture requirement for Military, whether mobility, encryption requirements.  
It should be assumed for this exercise only publicly available communications & encryption will be used. However, there are plenty of examples that can be utilized without the acquisition of a TAClane or LinkX communications.  

WIFI Router (1)  
Edge Server (1)  
Sensors (3)  

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
~~~

#### Software: ####

Motion v5 
: Motion is a program that monitors the signal from video cameras and detects changes in the images.

NGINX 
: Webserver configuration option which after Apache Tomcat is very common

MariaDB 
: Selected to provide additional application with a Published STIG
