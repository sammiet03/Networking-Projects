### Configuring VLANs 

- Standard VLAN ID range: 1-1001
- Extended VLAN ID range: 1006-4094, only on newer Cisco devices

##### Creating a VLAN and assigning interfaces
```
SW1(config)#vlan 10
SW1(config-vlan)# name Engineering 
SW1(config)# int g0/2
SW1(config-if)# switchport mode access 
SW1(config-if)# switchport access vlan 10
```

##### Checking the VLAN configuration
```
#show vlan brief 
#show vlan
```

#### Disabling a VLAN
```
SW1(config)#vlan 10 
SW1(config-vlan)#shutdown 

OR

SW1(config)# shutdown vlan 10 
```
