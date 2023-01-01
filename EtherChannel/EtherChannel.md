### Configuring L2 EtherChannel 

##### What is an EtherChannel?
- An EtherChannel allows you to bundle physical links together that will act as a single virtual link that can forward traffic. 
- Configuring an EtherChannel provides redundancy because if one of the bundled links fail, the remaining links will remain available.
- -	A port channel switch-to-switch technique for grouping several Fast Ethernet or Gigabit Ethernet ports into 1 logical channel 
-	Layer 2 STP and Layer 3 routing protocols will treat bundled links as one – stops STP from performing blocking
-	Single adjacency across the link can be formed


##### Configuring an EtherChannel 
```
(config-if)#channel-group 1 mode on 
```

##### Checking an EtherChannel status
```
#show etherchannel 1 summary - this will show summary status on the state, ports bundled in specified EtherChannel ID

AND

#show etherchannel 1 port-channel - this will show detailed information 
```

- EtherChannel mode ON, is used to manually bundle physical links together.
- But there are 2 protocols that can automatically bundle these physical links together through auto-negotiation.
- The 2 protocols are PAgP and LACP

##### PAgP
- Port Aggregation Protocol, is a Cisco-proprietary protocol. 
- Modes are Auto/Desirable
- At least one side of the link must be set to initiate auto-negotiation, while the other can be set to wait.
- Bundle up to 8 ports active between switches 
- Links must have same speed, duplex settings, and VLAN configuration 
- Send packets every 30 seconds to manage link consistency, any link additions, and failures



##### Configuration using PAgP
```
(config-if)# channel-group 1 mode desirable
(config-if)# channel-group 1 mode auto 
```

##### LACP
- Link Aggregation Control Protocol, IEEE standard 
- Modes are Active/Passive

```
(config-if)#channel-group 1 mode active
(config-if)#channel-group 1 mode passive
```
