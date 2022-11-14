## Simple Configuration for a Cisco Switch and Router 

##### Simple Network Topology Used in this Demonstration

![My Image](https://github.com/sammiet03/Networking-Projects/blob/main/Simple%20Configuration/Simple%20Configuration.PNG)

##### Addressing Table for our Network
| Device | Interface | IP Address | Subnet Mask | Default Gateway | 
| ------ | --------- | ---------- | ----------- | --------------- |
| PC0    |           | 192.168.1.2   | 255.255.255.0 | 192.168.1.1 |
| PC1    |           | 192.168.2.1   | 255.255.255.0 | 192.168.2.1 |
| R0     | G0/0/0    | 192.168.1.1   | 255.255.255.0 |             |
| R0     | G0/0/1    | 192.168.2.1   | 255.255.255.0 |             |

##### Steps for Configuring a Cisco Switch 
1. The initial command prompt will show "Switch>" 
2. Type "enable" next to it and press enter 
3. This will take you into Global Configuration mode 
4. Enter the configuration commands one per line 
5. Switch# configure terminal 
6. Switch(config)# hostname switch 
7. SwitchIconfig)# enable secret cisco 

##### Steps for Configuring a Cisco Router
