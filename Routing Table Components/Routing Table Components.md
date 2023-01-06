### Routing Table Components 

##### Routing Protocol Code
-	L – local
-	C – connected 
-	S – static
-	R – rip
-	I – IGRP 
-	D – EIGRP
-	O – OSPF

##### Types of Routes 
- **Default route (gateway of last resort)** – where packets will be sent if no specific route for the destination network is listed in the routing table, if there’s no default route all packets with destination address not found are discarded.
- **Connected route (C)** – subnets directly connected to a router’s interface 
- **Local route (L)** - /32
- **Floating static route** – a static route that has their AD value manipulated, can be utilized with one more static route, or they can be used together with dynamic routing protocols, both cases floating static route is backup route 
- **Network route** – route has subnet mask equal to that of the classful mask, example 192.168.0.1/24
- **Host route (local)** – used to route traffic to a specific host – subnet mask will always be in all 1’s IPv4 /32 or IPv6 /128


##### Route Selection Process
1. Longest prefix match – when 2 or more routes match a given destination IP address, 
the one with the longest (most specific) prefix is selected
2. AD - Administrative Distance - when a router has multiple routes to the exact same network and prefix, 
the one with the lowest AD is selected and installed in the routing table
3. Metric - when a router has multiple routes to exact same network and prefix with the same 
AD the one with the best metric is selected and installed in the routing table

##### Administrative Distance 

| Route Type | AD |
| ---------- | -- |
| Directly Connected | 0 |
| Static     | 1 |
| EIGRP Summary Route | 5 |
| eBGP | 20 |
| Internal EIGRP | 90 |
| IGRP | 100 |
| OSPF | 110 |
| IS-IS | 115 |
| RIP | 120 |
| External EIGRP | 170 |
| iBGP | 200 |
| DHCP Default Gateway | 254 |
| Unknown | 255 |

