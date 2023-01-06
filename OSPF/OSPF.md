### Open Shortest Path First 

##### OSPF – open standard 
-	Dijkstra’s algorithm to construct shortest path tree and follows that by populating the routing table with the best paths 
-	Supports multiple, equal-cost routes to same destination and both IPv4/IPv6
-	OSPF best features allows for creation of areas and autonomous systems, minimizes routing update traffic, highly flexible, versatile, and scalable, supports VLSM/CIDR, offers unlimited hop count, open standard = multi-vendor deployment 
-	Hierarchical design – to decrease routing overhead, speed up convergence, confine network instability to single areas of the network 
-	Backbone area = 0 – all other areas should connect to it 
-	Area border router (ABR) – router that connects to other areas to the backbone area within an autonomous system, must have at least one of their interfaces connected to area 0  
-	Autonomous system boundary router (ASBR) – OSPF runs great inside an autonomous system but can also connect multiple autonomous systems together. Router that connects these ASs is called ASBR
-	Link – a network or router interface assigned to any given network 

##### Neighbor adjacencies
- two or more routers that have an interface on a common network, must have common configurations to be able to establish a neighbor relationship, ALL of these must be configured exactly the same way: Area ID, Stub area flag, authentication password (if using one), Hello and Dead intervals
-	Adjacency – relationship between 2 OSPF routers that permits the direct exchange of route updates. In multi-access networks, routers form adjacencies with designated and backup designated routers. In point-to-point and point-to-multipoint networks, routers form adjacencies with the router on the opposite side of connection 
-	DR – designated router is elected whenever OSPF routers are connected to same broadcast network to minimize the number of adjacencies formed and to publicize received routing information to and from the remaining routers on broadcast network or link. 
-	BDR – backup designated router – hot standby for the DR on broadcast, or multi-access, links. BDR receives all routing updates from OSPF adjacency routers but does not disperse LSA updates 

##### OSPF Operation 
-	Neighbor and adjacency initialization 
    - Once router determines interfaces have been configured for OSPF, it will check if they’re active and begin sending hello packets
    - Hello protocol is used to discover neighbors, establish adjacencies, and maintain relationships with other OSPF routers
    - Hello packets sent out periodically, address used 224.0.0.5 multicast
    -	Broadcast and point-to-point send Hellos every 10 seconds
    -	Non-broadcast and point-to-multipoint send Hellos every 30 seconds
-	LSA flooding
    -	Method OSPF uses to share routing information through LSU (link state updates) 
    -	LSA information containing link-state data is shared with all OSPF routers within an area
    -	Network topology is created from LSA updates and flooding is used so all OSPF routers have same topology map to make SPF calculations 
    - Flooding is achieved through use of reserved multicast address: 
        - Point-to-point - 224.0.0.5 – all SPF routers
        - Broadcast – 224.0.0.6 – all D routers
-	SPF tree calculation 
    - OSPF metric is cost – reference bandwidth/interface bandwidth, reference bandwidth default = 100 Mbps 

##### 5 OSPF Network Types and Neighbors 
| Name | 	DB/BDR elections |	Manual neighbors |	Hello/Dead timers |	Command	| Default for |
| ---- | ----------------- | ----------------- | ------------------ | ------- | ----------- |
|Broadcast | Yes |	No |	10/40 |	(config-if)#ip ospf network broadcast	 | Ethernet, FDDI |
| Non-broadcast	 | Yes | 	Yes |	30/120	| (config-if)#ip ospf network non-broadcast |	X.25, Frame Relay|
| Point-to-point |	No | 	No | 	10/40 |	(config-if)#ip ospf network point-to-point | 	PPP, HDLC |
| Point-to-multipoint broadcast	| No | 	No |  30/120 | 	(config-if)#ip ospf network point-to-multipoint | - |	
| Point-to-multipoint non-broadcast	 | No	| Yes	 | 30/120	| (config-if)#ip ospf network point-to-multipoint non-broadcast | - |	


##### Broadcast (DR/BDR selection)
-	Elections for DR won based upon router’s priority level, 1 with the highest priority becomes DR
-	If tie, router ID will be used to break it 


##### Two simple commands for single-area configuration command 
```
Router ospf process-id
network x.x.x.x y.y.y.y area Z
```
