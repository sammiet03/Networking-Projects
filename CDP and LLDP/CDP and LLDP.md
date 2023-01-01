### CDP
- Cisco Discovery Protocol
- Cisco Proprietary 
- Administrator can gather hardware and protocol information about neighboring devices
- To discover information, Cisco devices send CDP messages out each of their interfaces
- Messages contain information such as, hostname, network, data link addresses, device model, IOS version, etc.

##### To display information about directly connected devices 
```
R1# show cdp neighbors 

or 

R1# show cdp neighbors detail 
```

### LLDP
- Link Layer Discovery Protocol
- Vendor-neutral link layer protocol defined by 802.1AB IEEE standard
- Used by network devices to advertise their identity, capabilities, and neighbors on a local network

##### To enable on Cisco devices 
```
R1(config)# lldp run 
```

##### To display information about LLDP Neighbors 
```
R1# show lldp neighbors

or 

R1# show lldp neighbors detail 

or 

R1# show lldp 

for global information 
```

##### To configure whether you would like your device to send or receive LLDP packets on a particular interface
```
R1(config-if)# no lldp transmit
R1(config-if)# no lldp receive 
```

