### DTP
- Dynamic Trunking Protocol, Cisco Proprietary 
- Used to Automatically negotiate trunks between Cisco Switches 
- Trunk negotiations are managed by DTP only if the port is directly connected to each other

### DTP Modes 
**switchport mode access**
- does not act as a trunk
- only allows one VLAN through port

**switchport mode trunk** 
- enables the interface to be set in permanent trunking mode 
- establishes negotiations to convert neighboring link to become a trunk link


**switchport mode dynamic auto**
- interface will passively wait to receive a negotiation message to make itself a trunk, will become trunk if neighboring interface is set to trunk or dynamic desirable

**switchport mode dynamic desirable**
- lets port initiate trunking with another port by sending negotiation messages to dynamically choose whether to start trunking,
interface becomes trunk port if neighboring interface is set to trunk, dynamic desirable, or dynamic auto

**switchport mode nonegotiate**
- disabled DTP 


| **Trunk Mode** | Dynamic Auto | Dynamic Desirable | Trunk | Access |
| -------------- | ------------ | ----------------- | ----- | ------ |
| Dynamic Auto   |     Access   |       Trunk       | Trunk | Access |
| Dynamic Desirable|   Trunk    |       Trunk       | Trunk | Access |
|    Trunk       |     Trunk    |       Trunk       | Trunk |   -    |
|    Access      |     Access   |       Access      |   -   | Access |

##### DTP Configuration
```
SW1(config)# vlan 199
SW1(config-vlan)# name Native 
SW1(config)# int g0/1
SW1(config-if)# switchport trunk encap dot1q
SW1(config-if)# switchport mode trunk 
SW1(config-if)# switchport trunk native vlan 199 
SW1(config)# int g0/2
SW1(config-if)# switchport trunk encap dot1q
SW1(config-if)# switchport mode trunk 
```

### VTP
- VLAN Trunking Protocol, synchronizes VLAN information between switches 
- Allows switches to advertise VLAN information such as, IDs enabled and names, and other switches to receive it and update their configuration.
- VLAN information can be removed, added, or updated. 
- It is recommended to disable VTP as it can misconfigure or remove a VLAN config in the whole network if there is an error. 

##### VTP Modes 
```
(config)# vtp mode {server | client | transparent | off}
```

##### VTP Server
- Creates, modifies, deletes VLANS
- Stores VLAN information locally in NVRAM
- Originates and forwards VTP advertisements 
- Synchornizes VTP information 

##### VTP Client
- Listens for VTP advertisements and forwards
- Client's VTP database dependent on VTP
- Cannot add, modify, or delete VLANs locally 
- Does not store VLAN information 


###### VTP Transparent 
- Does not participate in VTP 
- Does not originate VTP advertisements or populate VLAN database 
- Does forward VTP advertisements
- Maintains its own VLAN database and stores it in NVRAM
- The recommended mode

##### To set VTP Domain and Version 
```
(config)#vtp domain ExampleDomain 
(config)#vtp version 2
```

##### Checking VTP status 
```
#show vtp status 
```
