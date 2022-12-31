### TCP and UDP 

##### TCP (Transmission Control Protocol)
-	Before connection between two hosts must be established through three-way handshake before sending data 
-	Three-way handshake
    - SYN – host sends packet to destination host to initiate connection, packet contains random sequence number that marks beginning of sequence numbers for data that sender will transmit 
    - SYN, ACK – receiver responds with its own sequence number, response also includes acknowledgement number, which is senders sequence number increased by 1 
    - ACK – sender acknowledges the response of receiver by sending acknowledgement number, which is receivers sequence number increased by 1 
-	After data transmission ended, TCP will terminate connection between 2 endpoints in FAFA:
    - FIN – sender sends TCP segment with the FIN (finished) flag set to 1 to receiver 
    - ACK – receiver receives the TCP segment and acknowledges it with the ACK segment 
    - FIN – receiver sends it own TCP segment with the FIN flag set to 1 to sender to terminate connection 
    - ACK – client acknowledges senders FIN segment and closes connection 
-	TCP header = 24 bytes long, Consists of:
    - Source port
    - Destination port
    - Sequence number – used to identify each byte of data 
    - Acknowledgment number 
    - Header length
    - Reserved – always set to 0
    - Flags – used to set up and terminate a session
    - Window – window size sender is willing to accept
    - Checksum – used for error-checking of header and data 
    - Urgent – indicates offset from current sequence number, where segment of non-urgent data begins
    - Options – maximum segment size (MSS) or window scaling

### UDP (User Datagram Protocol)
-	Does not sequence data and does not care about the order in which segments arrive at the destination
-	UDP header – 8 bytes: source, destination port, length, checksum 


##### Common Ports 

TCP
- FTP, 20, 21
- SSH, 25
- Telnet, 23
- SMTP, 25
- HTTP, 80 
- HTTPS, 443
- POP3, 110
- IMAP4, 143

UDP
- DHCP, 67, 68
- TFTP, 69
- NTP, 123
- SNMP, 161 
