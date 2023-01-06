### Routing Information Protocol (RIP)
- Used for small networks because it is easy to configure and maintain
- Administrative Distance of 120
- Metric: hop count
- V1 updates forwarded to address 255.255.255.255 every 30 seconds
- Maximum hop count of 15, anything higher destination is unreachable 
- RIPv2
    - RIPv2 capable of advertising subnet masks and uses multicast to send routing updates, version 1 doesn’t advertise subnet masks and uses broadcast for updates. 
    - V2 sends entire routing table every 30 seconds, uses multicast address of 224.0.0.9 to send routing updates, supports authentication and triggered updates
    - Support CIDR, Summarization, and Authentication 




##### Configuration
```
R1(config)#ip route 0.0.0.0 0.0.0.0 50.50.50.1 
R1(config)#router rip
R1(config-router)#default-information originate

To check configuration 
#show ip route rip 

To configure RIPv2
#version 2 – for RIPv2 
```
