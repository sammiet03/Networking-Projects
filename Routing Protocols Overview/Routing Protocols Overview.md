### Dynamic Routing Protocols Overview 

##### Purpose of Dynamic Routing Protocols
- Discovery of remote networks
- Maintain up-to-date routing information
- Choosing the best path to destination networks
- Ability to find a new best path if current path is no longer available

##### 2 Categories of Dynamic Routing Protocols
- Interior Gateway Protocols (IGP)
    - Used for routing within an Autonomous System (AS)
- Exterior Gateway Protocols (EGP)
    - Used for routing between Autonomous Systems  

##### IGP
- There are 2 categories of IGPs 
    - Distance Vector: routes are advertised by distance (how far it is to destination network based on a metric such as hop count, costs, bandwidth, delay) and Vector 
(specifies the direction of the next-hop router or exit interface to reach destination)
        - Distance Vector Protocols Include: RIP, IGRP, EIGRP 
    - Link-State: a router uses link-state information received from other routers to create a topology map, select the best path to all destination networks in the topology
        - Link-state routing protocols do not use periodic updates, updates are only sent when there is a change in the topology
        - Link-state Protocols Include: OSPF and IS-IS
