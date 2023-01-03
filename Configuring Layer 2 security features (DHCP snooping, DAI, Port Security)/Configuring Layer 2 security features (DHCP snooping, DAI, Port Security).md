###  Configuring Layer 2 security features (DHCP snooping, DAI, Port Security)

##### Port security 
-	Switchport mode access, Switchport port-security, do show port-security int f0/0 – we are assured that no other device can connect once our hosts in interfaces are connected 
- Switchport port-security – enabled port security with maximum MAC address of 1 and violation of shutdown 
- Defend access layer by restricting a port to a specific set of MAC addresses 

##### DHCP Snooping 
-	Layer 2 security feature – validates DHCP messages by acting like a firewall between trusted hosts and untrusted DHCP server 
-	To stop rogue DHCP servers within the network, switch interfaces are configured as trusted or untrusted – trusted interfaces allow all types of DHCP messages – untrusted interfaces only permit requests 
-	With DHCP snooping enabled – a switch builds a DHCP snooping binding database – includes MAC and IP of host, DHCP lease time, binding type, VLAN, interface – DAI also uses DHCP snooping binding database 

##### DAI (Dynamic ARP inspection) – tracks IP to MAC bindings from DHCP transactions to protect against ARP poisoning – you need DHCP snooping to build MAC to IP bindings for DAI validation 

##### Identity-based networking – allows us to verify users when they connect to a switch port by authenticating them, placing them in right VLAN and applying security and QoS policies based on identity
- 802.1x permits implementation of identity-based networking – there are 3 roles
    - Client – supplicant, software that runs on a client 
    - Authenticator – switch, VPN server, or WAP, controls physical access to network and proxy between client and authentication server
    - Authentication server (RADIUS) – authenticates each client before making any services available 
