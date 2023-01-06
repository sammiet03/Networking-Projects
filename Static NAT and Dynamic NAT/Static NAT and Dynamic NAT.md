### Static NAT and Dynamic NAT

##### 3 Types of NAT 
- Static NAT (one-to-one) – one-to-one mapping between local and global addresses – static requires you to have 1 real IP address for every host on your network
- Dynamic NAT (many-to-many) – gives your ability to map an unregistered IP address to a registers IP address from a pool of registered IP addresses 
- Overloading (one-to-many) – most popular, maps multiple unregistered IP addresses to a single registered Ip address by using different source ports
     - Also known as PAT (port address translation) – allows you to permit thousands of users to connect to the Internet using only 1 real global IP address 

##### NAT Names
- **Inside Local addresses** – one used before NAT translation – private address of the sending host that’s attempting to get to Internet
- **Outside local address** – router interface connected to your ISP and is public address used as the packet begins it journey 
- **Inside global** – source host address used after translation to get onto internet – also actual internet address
- **Outside global** – address outside destination host and real internet address 

##### Static NAT Configuration 
```
#ip nat inside source static 10.1.1.1 170.46.2.2 - configures static translation between inside local IP 10.1.1.1 and outside global IP 170.46.2.2
#int fa0
#ip add 10.1.1.10 255.255.255.0
#ip nat inside 
#int s0
#ip add 170.46.2.1 255.255.255.0
```
