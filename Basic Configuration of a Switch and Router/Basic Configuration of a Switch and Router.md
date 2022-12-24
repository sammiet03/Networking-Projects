### Basic Configuration of a Switch and Router

#### Configuring Hostnames of the routers and switches to an appropriate name

```
Switch1> enable
Switch1# config t
Switch1(config)# hostname SW1
SW1(config)# end 
SW1#
```
- These same steps can be repeated on a router.


#### Assigning an IP address to a Switch 

- On switches, IP addresses are configured under a logical interface such as a management domain or a VLAN. The default Native VLAN for any switch is VLAN 1. It is a recommended security practice to change the Native VLAN to a different VLAN number other than VLAN 1. But in this example, we will stick with VLAN 1. 
```
SW1> enable
SW1# config t
SW1(config)# int vlan 1
SW1(config-if)# ip address 10.0.0.1 255.255.255.0
SW1(config-if)# no shutdown 
```


#### Assigning an IP address to a Router 

```
R1> enable
R1# config t
R1(config)# int f0/1
R1(config-if)# ip address 10.0.2.1 255.255.255.0
R1(config-if)# no shutdown
```
- The "no shutdown" command will bring the interface up (turn on).

#### Applying password protection onto our Switches and Routers 

- Enable password command is used for securing privilege mode (SW1#) with a clear text password

```
SW1> en
SW1# config t
SW1(config)# enable password NetworkingIsCool!
SW1(config)# end
SW1#
```

- Enable secret command is also used to secure privileged mode, but it will encrypt the password with a MD5 algorithm. This means that if you perform the #show  run command, the password in the output of the command will show that a password has been configured but the password will show up encrypted. 

```
R1> en
R1# config t
R1(config)# enable secret NetworkingIsCool!
R1(config)# end
R1#
```

- Here is the output of the #show run command on R1, after using the enable secret command

```
Router#show run 
Building configuration...

Current configuration : 705 bytes
!
version 16.6.4
no service timestamps log datetime msec
no service timestamps debug datetime msec
no service password-encryption
!
hostname Router
!
!
!
enable secret 5 $1$mERr$/Q/mbs3O9oHsKR7rNG4e81
```

- To secure access through the console port you can also configure a password 

```
SW1> en
SW1# config t
SW1(config)# line console 0 
SW1(config-line)# password NetworkingIsCool!
SW1(config-line)# login 
```

- You can also configure a password through VTY lines (Telnet or SSH)

```
SW1> en
SW1# config t
SW1(config)# line vty 0 5 
SW1(config-line)# password NetworkingIsCool!
Sw1(config-line)# exit
```

#### Securing all plain text passwords configured in the running configuration 
- Use the service password-encryption command to use the MD5 hashing algorithm to encrypt all clear text passwords in the running config
```
R1> en 
R1# config t
R1(config)# service password-encryption
R1(config)# end
R1#
```
#### Half Duplex and Full Duplex
- Duplex communication system is a point-to-point system where 2 devices can communicate with each other in both direction. 
- Half duplex means that a port interface can only send data when it is not receiving data. It cannot send and receive data at the same time. 
- Full duplex means that all nodes can send and receive on their port at the same time. 

#### Configuration for Half Duplex on a Switch
```
SW1(config)# int fa0/3
SW1(config-if)# speed 100 
SW1(config-if)# duplex half
```

#### Configuration for Full Duplex on a Switch
```
SW1(config)# int fa0/5
SW1(config-if)# speed 1000
SW1(config-if)# duplex full 
```

#### Configuring Speed
```
(config-if)#speed {10 | 100 | 1000 | auto}
```



