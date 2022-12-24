### Configuring L2 EtherChannel 

##### What is an EtherChannel?
- An EtherChannel allows you to bundle physical links together that will act as a single virtual link that can forward traffic. 
- Configuring an EtherChannel provides redundancy because if one of the bundled links fail, the remaining links will remain available.

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
