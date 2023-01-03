### Security Concepts

##### Threats, Vulnerabilities, Exploits, and Mitigation Techniques
-	Reconnaissance Attacks – unauthorized familiarization session – attacker on reconnaissance for discovery – mapping network, its resources, systems, and vulnerabilities – information gathered will be used later
-	Access attacks – waged against networks or systems to retrieve data, gain access, and/or escalate access privilege 
-	Denial of Service (DoS) attacks – deny legitimate users from accessing network resources – sole purpose disable or corrupt network services – result DoS crash a system or slow it down – usually aimed at web servers
-	Eavesdropping – network snooping and packet sniffing, act of hacker “listening in” to your system 
-	Smurfing – sends large amount of ICMP echo (ping) traffic to IP broadcast address – framed host gets blamed for attack – targets IP address used as source address in the ping and all system reply to target eating up its resources
-	Brute-force attack – program that repeatedly attempts to identify a user account and/or password 
-	Man-in-the-Middle attack – person between you and the network you are connected to gathering everything you are sent and received – implemented by using network packet sniffers, routing protocols, or Transport protocols
-	HTML attack – exploits several new technologies: HTML specification, web browser functionality, and HTTP – pass destructive programs across the network and load them through a user’s browser
-	Malware:
    - Trojan Horse – creates substitute for common program, duping users into thinking they are using valid program – gives attack power to monitor login attempts and capture user account and password information 
    - Worms and Viruses – spread and infect multiple systems – differentiator is that viruses require some form of human interaction to spread, and worms do that on their own 
    - Spyware – collects private user data, including browsing history or keyboard input

##### Security Program Elements 
-	User Awareness – skilled enough to avoid being set up and trapped – should be able to identify and understand phishing/pharming, shoulder surfing, identity theft, and dumpster diving 
-	Training – best countermeasure against social engineering threats is to provide user security awareness training – caution users against using any links embedded in email
-	Physical access control:
    - Mantrap – series of 2 doors with a small room between them – the person who wants in is authenticated at the first door and then allowed into the room – guard visually identifying person is required to permit them through 2nd door 
    - Badge reader – RFID badges or cards 
    - Smart card – fancy badge or card that gives you access to myriad resources, including buildings, parking lots and computers – embedded with you identity and access privilege information and each area or device you access has a card scanner – tough to counterfeit – modern smart cards require a password or PIN to activate it plus encryption to protect card’s contents

##### Configure device access control using local passwords
-	Used to configure a password when user mode is accessed through console port, auxiliary port, or via Telnet – Router>
    - Console – sets a console user-mode password
    - Auxiliary – sets a password on the Aux line, used for modem connection 
    - Telnet (VTY) – sets a Telnet password on the device, if password isn’t set then by default Telnet can’t be used
-	Used to set password for securing privileged mode – Router#
    - Enable password
    - Enable secret 

##### Security Password Policies Elements
-	Password expiration = you should require users to set a new password every 30 days and prevent them from reusing old password 
-	Password Complexity = both upper and lowercase letters, numbers, and symbols
-	Single sign-on (SSO) – when user logs into domain, domain controller issues them an access token, access token contains a list of all resources which they are permitted access 
-	Digital certificate – provides entity, with credentials to prove its identity and associate’s identity with a public key, at minimum digital certification must provide serial number, issuer, the subject (owner) and public key 
    - Certificate is text document that ties a user account to a public and private key pair created by a certificate server or certificate authority (CA)


##### AAA
Authentication, Authorization, and Accounting 
- Used to manage activity of the user to a network that it wants to access by AAA mechanism
- Used widely on routers, switches, firewalls 
Authentication- Who wants to access the network?
- Credentials of user are being challenged by asking for username/pass, which is encrypted using a hashing algorithm

Authorization – What is the user allowed to access?
- Determines what the specific user is allowed to do and access within the premises of the network 
- Users are categorized to know what type of operations they are allowed to perform such as an Administrator or Guest 
- User profiles configured and controlled from the AAA server

Accounting – taking note of everything the user is doing within the network 
- Logs session statistics and auditing usage information that is being used for authorization control, billing invoice, resource utilization, trend analysis, and planning data capacity of the business operations
Protocols:
- RADIUS – Remote Authentication Dial-In User Service – ports UDP 1645 and UDP 1812 
    - Provides centralized AAA management for users who connect and use Network Access Server (NAS) 
    - Client/server protocol and software enables remote access servers to communicate with a central server to perform AAA operations for remote users. 
- TACACS+ - Terminal Access Controller Access-Control System Plus 
    - Remote authentication protocol
    - Allows a remote access server to communicate with an authentication server to validate user access onto the network 
    - Permits client to accept a username and password and pass a query 
