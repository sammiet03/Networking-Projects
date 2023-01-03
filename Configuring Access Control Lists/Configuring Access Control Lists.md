### Configuring Access Control Lists

-	Access list – list of conditions that categorize packets to control network traffic 
    - To filter unwanted packets when implementing security policies 
    - Can be applied either inbound or outbound traffic on any interface
-	Rules a packet follows when it’s being compared with an access list:
    - Packet always compared with each line of access list in sequential order – it will always start with the first line in the access list – 1, 2, 3
    -	Packet is compared with lines of the access list only until a match is made – once it matches condition on a line of the access list, packet is acted upon, and no further comparisons take place
    -	Implicit deny at the end of each access list – means that if a packet doesn’t match the condition on any access list the packet will be discarded 

##### 2 Main types of Access Lists – Creating an ACL
-	Standard access lists (1-99 and 1300-1999) – use only source IP address in an IP packet as the condition test. All decisions made based on source IP – means standard access lists permit or deny an entire suit of protocols
-	Extended access lists (100-199 and 2000-2699) – can evaluate many of other fields in layer 3 and layer 4 headers of an IP packet – can evaluate source and destination IP addresses, the protocol field in the network layer header, and port number at transport layer header 
-	Named access lists – can be either standard or extended 

##### Inbound access lists – packets are processed through the ACL before being routed to the outbound interface – any packets denied won’t be routed 
##### Outbound access lists – packets routed to outbound interface and then processed through the access list before being queued 

### Rules when placing ACLs!
- Place IP standard access lists as close to the destination as possible 
- Place IP extended access lists as close to the source as possible 
