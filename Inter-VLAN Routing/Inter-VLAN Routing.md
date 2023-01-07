### Inter-VLAN Routing
- Since hosts in one VLAN cannot communicate with hosts in another VLAN. They need to use a router or a Layer 3 switch to provide routing services.
- There are 3 Inter-VLAN routing options:
    - Legacy Inter-VLAN routing 
    - Router on a stick (ROAS)
    - Layer 3 switch with switched virtual interfaces (SVIs)

##### Legacy Inter-VLAN Routing
- This method uses a router with multiple Ethernet interfaces
- Each router interface is connected to a switch port in different VLANs
- The router interfaces serve as the default gateways to the local hosts on the VLAN subnet 
- This solution does not scale well 

##### Router on a Stick (ROAS)
- Requires only one physical Ethernet interface to route traffic between multiple VLANs on a network
- The Ethernet interface is configured as an 802.1Q trunk and connected to a trunk port on a Layer 2 switch 
- The router interface is then configured using subinterfaces to identify routable VLANs
- This solution is acceptable for small to medium sized networks

##### Layer 3 Switch Method
- This method involves a Layer 3 switch and SVIs 
- SVIs are created and perform the same functions for the VLAN as a router interface would
- Advantages:
    - Much faster than ROAS because everything is hardware switched and routed 
    - There is no need for external links from the switch to the router for routing 
    - Latency is lower because data does not need to leave the switch to be routed to a different network
    - More commonly deployed in a campus LAN than routers 
- Only disadvantage is that Layer 3 switches are more expensive 
