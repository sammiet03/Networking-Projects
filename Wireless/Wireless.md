### Wireless 
-	Nonoverlapping channels 
o	1, 6, 11channels in 2.4 GHz band, honeycomb pattern to provide complete coverage without interference
o	2.4 GHz band provides further reach in open space and better penetration of obstacles such as walls
-	*Wi-Fi 6 (802.11ax) has expanded spectrum range to include a band in the 6 GHz
-	CSMA/CA is used in wireless networks to avoid collisions 
o	Device will wait for other devices to stop transmitting before it transmits data itself
-	CSMA/CD is used in wired networks to detect and recover from collisions 

| Standard | Frequency | Max Data | Alternate Name |
| -------- | --------- | -------- | -------------- |
|  802.11	 |  2.4 GHz	 |  2 Mbps  |        -       |	
| 802.11b  |  2.4 GHz	 |  11 Mbps |	       -       |
| 802.11a	 |   5 GHz	 |  54 Mbps |	       -       |
| 802.11g	 |  2.4 GHz  |	54 Mbps	|        -       |
| 802.11n	 | 2.4/5 GHz |	600 Mbps |	  Wi-Fi 4 |
| 802.11ac |	5 GHz	   | 6.93 Gbps |    Wi-Fi 5 |
| 802.11az | 2.4/5/6 GHz | 4x802.11ac | Wi-Fi 6 |

Service Sets
-	Groups of wireless network devices 
-	3 types: independent, infrastructure, mesh 

##### IBSS (Independent Basic Service Set)
-	Wireless network in which 2 or more wireless devices connect directly without using an AP
-	Also called AD Hoc network 

##### BSS (Basic Service Set)
-	Clients connect to each other via an AP but not directly to each other 
-	BSSID (basic service set ID) – used to identify the AP
- Other APs can use same SSID but not BSSID
- BSSID is MAC of the AP radio 
-	Area around an AP where signal is useable is called a BSA (basic service area)
-	An infrastructure service set 

##### ESS (Extended Service Set)
-	To create larger wireless LANs beyond range of a single AP
-	APs with their own BSS are connected by wired network 
- Each BSS uses same SSID
- Each BSS has unique BSSID
- Each BSS uses different channel to avoid interference 
-	ROAMING 
-	BSAs should overlap by 10-15%

##### MBSS (Mesh Basic Service Set)
-	Used in situations where it’s difficult to run an Ethernet connection to every AP
-	Mesh APs use 2 radios: 1 to provide BSS to wireless clients, and 1 to form a ‘backhaul network’ which is used to bridge traffic from AP to AP
-	At least 1 AP is connected to wired network, and this is the RAP (Root AP)
-	Other APs are called MAPs (Mesh APs) 

### Wireless Access Points
802.11 FRAME FORMAT
FC | Duration/ID | Add1 | Add2 | Add3 | SC | Add4 | QoS C | HT C | Frame Body (packet) | FCS

802.11 Association Process
-	must be authenticated and associated with AP to send traffic through it 

2 ways a station can scan for a BSS:
-	active scanning: station sends probe requests and listens for a probe response from an AP
-	passive scanning: stations listens for beacon messages from an AP

WLC – device that cooperates with wireless LWAPs to create a wireless LAN by performing some control functions for each LWAP and forwarding data between each LWAP and wired LAN
- you can configure a maximum number of 512 WLANs on a WLC

### WAP Modes 
1.	<ins>Autonomous</ins> – no central monitoring or management of APs – small networks – connect to wired network with trunk link 
-	Don’t rely on WLC 
-	Configured by CLI, SSH/telnet, or web GUI
-	IP address for remote management 
-	RF parameters manually configured 
-	Security policies and QoS rules handled individually by each AP
-	Connect to wired network with trunk link 
-	Other MODES: repeater, outdoor bridge, workgroup bridge 

2.	<ins>Lightweight</ins> – split-MAC architecture – CAPWAP – APs connect to switch access ports, connect to wired network with access link
-	Functions of AP can be split between AP and WLC
-	Handle real time operations like transmitting/receiving RF traffic, encryption/decryption of traffic, sending out beacons/probes
-	RF management, security/QoS management, client authentication, client association/roaming management 
-	WLC use to centrally configure LAPs 
-	WLC can be in same subnet/VLAN as LAP it manages or in different subnet/VLAN
-	Authenticate with X.509 certificates 
-	Use protocol <ins>CAPWAP (control and provisioning of WAPs)</ins> to communicate 
     - 2 tunnels created between each AP and the WLC
     - Control tunnel (UDP port 5246) – used to configure APs, and control operations, all traffic in this tunnel encrypted 
     - Data tunnel (UDP port 5247) – all traffic from wireless client is sent through this tunnel to WLC, doesn’t go through wired network, traffic not encrypted but you can with DTLS

-	Benefits of Split-MAC architecture:
     - Scalability
     - Dynamic channel assignment 
     - Transmit power optimization 
     - Self-healing wireless coverage 
     - Seamless roaming
     - Client load balancing
     - Security/QoS management


-	<ins>Various MODES:</ins>
     - Local: default mode where AP offers a BSS for clients 
     - FlexConnect – offers one or more BSS for clients, allows AP to locally switch traffic between wired and wireless networks if tunnels to the WLC go down
     - Sniffer – does not offer BSS, dedicated to capturing 802.11 frames and sending them to a device running packet software (Wireshark) 
     - Monitor – AP does not offer BSS for clients, dedicated to receiving 802.11 frames to detect ROGUE devices. 
     - Rogue Detector – AP does not use radio, listens to traffic on WIRED network only, but receives list of suspected rogue clients and AP MAC address from the WLC
     - SE-Connect (Spectrum Expert Connect): dedicated to RF spectrum analysis on all channels 
     - Bridge/Mesh: dedicated bridge between 2 sites 
     - Flex plus Bridge: adds FlexConnect functionality to the Bridge/Mesh mode, allows WAPs to locally forward traffic even if connectivity to WLC lost

3.	Cloud-based – between autonomous AP and Split-MAC architecture
-	Autonomous APs centrally managed in the cloud 
-	Cisco Meraki 
    - Dashboard can be used to configure APs, monitor network, generate performance reports, etc.
    - Meraki tells each AP what channel to use
    - Data traffic not sent to the cloud; it’s sent to wired network 

### WLC Deployments 
-	In split-MAC architecture 4 WLC deployment models:
-	Unified: WLC is a hardware appliance in central location of network, support 6000 APs 
-	Cloud-based: WLC is a VM running on a server, usually in private cloud in data center, 3000 APs
-	Embedded: WLC integrated within a switch, 200 APs
-	Mobility Express: WLC integrated within a AP, 100 APs

LAG
-	Link aggregation – partial implementation of 802.3ad, bundles all ports of the WLC into single port channel 
-	Controller manages redundancy and load balancing of all the APs across the ports 

