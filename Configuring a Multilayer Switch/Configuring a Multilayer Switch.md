### Configuring a Multilayer Switch

##### Network Topology 

##### Enable routing on MLS
```
MLS(config)# ip routing 
```

##### Adding VLANs 

```
MLS> en
MLS# config t
MLS(config)# vlan 10 
MLS(config-vlan)# vlan 20 
MLS(config-vlan)# vlan 30 
```

##### Configuring Trunk and Assigning Interfaces to appropriate VLANs
```
MLS(config)#int f0/1
MLS(config-if)# switchport trunk encapsulation dot1q
MLS(config-if)# switchport mode trunk 
MLS(config-if)# switchport access vlan 20 
```
- You will do this for each interface port you are going to use 

##### Assigning IP address to each VLAN 
```
MLS(config)# int vlan 10 
MLS(config-if)# ip address 192.168.1.1 255.255.255.0
MLS(config)# int vlan 20 
MLS(config-if)# ip address 192.168.2.1 255.255.255.0
MLS(config)# int vlan 30 
MLS(config-if)# ip address 192.168.3.1 255.255.255.0
```

