### Enhanced Interior Gateway Routing Protocol 
- Advanced distance vector routing protocol, evolution of earlier Cisco protocol called IGRP
- Supports classeless routing and VLSM, route summarization, incremental updates, load balancing, and other features
- Routers running EIGRP must become neighbors before exchanging routing information 
- EIGRP routers use multicast address of 224.0.0.10 to dynamically discover neighbors
- Each EIGRP router stores routing and topology information in 3 tables:
    - Neighbor table - stores information about EIGRP neighbors
    - Topology table - stores information learned from neighboring routes
    - Routing table - stores the best routes  
- Administrative Distance of: 90
- Routing Protocol Code: D
- Metric - bandwidth, delay, reliability and load 
- On LAN interfaces hellos sent every 5 seconds, on WAN interfaces every 60 seconds

##### Important EIGRP Terms
- Feasible distance (FD) - the metric of the best route to reach a network, listed in routing table
- Reported distance (RD) - metric advertised by neighboring router for specific route
- Successor - route with best metric to reach destination 
- Feasible successor - backup path to reach same destination that can be used immediately if successor route fails, backup routes stored in topology table

##### EIGRP Diffusing Update Algorithm (DUAL)
- used by EIGRP to select and maintain best route to each remote network 
- used for the following purposes:
    - discover backup route if there is one available
    - support VLSMs
    - perform dynamic route recoveres 
    - query neighbors for unknown alternate routes
    - send out queries for alternate routes 
- Requirements for DUAL to work:
    - EIGRP neighbors must be discovered
    - all transmitted EIGRP messages should be received correctly 
    - all changes and messages should be processed in the order in which they're detected  
