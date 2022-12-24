### Voice VLAN
- IP Phones can have a PC plugged directly into the back of them and the phone is plugged into a network switch. This allows the IP phone and PC
to be connected into the same network switch port. 
- The voice traffic from the phone is placed into a dedicated Voice VLAN and the data traffic from the PC is placed in an access VLAN.
- Phones have a built-in interface switch that trunks the voice VLAN traffic from the phone and the access VLAN traffic from the PC towards the rest of the network.

##### Configuration 
```
SW1(config)# vlan 10
SW1(config-vlan)# name PC
SW1(config)# vlan 11
SW1(config-vlan)# name Voice
SW1(config)#int g0/3
(config-if)# switchport mode access
(config-if)# switchport access vlan 10 
(config-if)# switchport voice vlan 11 
```

