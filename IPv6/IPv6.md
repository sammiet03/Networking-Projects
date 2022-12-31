### IPv6 Addressing 

##### 3 Types of IPv6 Addresses
-	Unicast – represents single interface – single host
-	Anycast – identifies one more interface
-	Multicast – represents a dynamic group of hosts – delivered to many interfaces

##### 3 Types of Unicast Addresses:
-	Global unicast – 200::/3
-	similar to IPv4 public IP addresses – assigned by IANA
-	001 | Global Routing Prefix | Subnet ID | Interface ID
-	001 = 3 bits  
-	Global routing prefix = 45 bits 
-	Subnet ID = 16 bits
-	Interface ID = 64 bits

-	Unique local – FD00::/8
-	similar to private IPv4 addresses 
-	FD | Global ID | Subnet ID | Interface ID
-	FD = 8 bits
-	Global ID = 40 bits
-	Subnet ID = 16 bits
-	Interface ID = 64 bits 

-	Link local – FE80::/10
-	used for sending packets over local subnet – routers don’t forward – IPv6 requires link-local address to be assigned to every network interface on which IPv6 protocol is enabled 
-	FE80:0000:0000:0000 | Interface ID
-	FE80 = 64 bits
-	Interface ID = 64 bits 

##### Multicast Addresses - FF00::/8
-	FF | Flag | Scope | Group ID
-	FF = 8 bits
-	Flag = 4 bits 
-	Scope = 4 bits 
-	Group ID = 112
-	Possible scope values:
-	1 – interface local
-	2 – link local
-	4 – admin local
-	5 – site local
-	8 – organization local 
-	E – global
-	Examples: FF02::/16 are multicast addresses intended to stay on local link 

##### Most Common Link Local Multicast Addresses 
-	All nodes on link – FF02::1
-	All routers on link – FF02::2
-	OSPF – FF02::5 and FF02::6
-	RIPv2 – FF02::9
-	EIGRP – FF02::A

##### IPv6 Modified EUI 64 
-	Extended Unique Identifier – method used to automatically configure IPv6 host addresses 
-	IPv6 device will use MAC address of its interface to generate a unique 64-bit interface ID

Steps 
1.	Take MAC split into 2 pieces 
2.	Insert FFFE in between 2 pieces so that we can have a 64-bit value because a MAC address is only 48 bits 
3.	Invert 7th bit of interface ID
