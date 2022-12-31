### IPv4 
-	32 bits 
-	Public IP addresses given by ISP
-	Private IP addresses – used in private networks for internal traffic within the LAN, not routable to internet 

| Class | First Octet Value |	Subnet Mask |
| ----- | ----------------- | ----------- |
|   A 	|       0-127	      |      /8     |
|   B	  |      128-191	    |     /16     |
|   C	  |      192-223	    |     /24     |
|   D	  |      224-239	    |      -      | 
|   E	  |      240-255	    |      -	    | 

Class D is used for -	Multicast 
Class E is used for - Experimental purposes

##### Special Addresses
-	0.0.0.0 /8 – used to communicate with local network
-	127.0.0.0 /8 – loopback 
-	169.254.0.0 /16 – link-local addresses (APIPA) 

##### Formula for the Number of usable IP addresses 
-	2^ (# of 0’s in the subnet mask) – 2

##### The Formula for the Number of subnets created 
-	2^(# of 1’s in the subnet mask)
