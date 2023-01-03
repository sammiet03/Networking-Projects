### Spanning-Tree Protocol 

##### Types of STP
- **STP** - 802.1d - Original standard for bridging and STP
    - Port states - listening, blocking, disabled
    - Port types - root and designated
    - Root switch - generates/sends hellos to all other switches 
- **PVST+** (Cisco default version) - Cisco enchancement for STP - provides separate 802.1d spanning-tree instance for each VLAN, multiple root bridges
- **RSTP** - 802.1w - enhanced BPDU exchange - faster network convergence 
    - STP port states listening, blocking, and disabled are merged into single state in RSTP called – discarding state 
    - Adds ports – root, designated, alternate and backup 
    -	Each switch can generate hellos 
- **MSTP** - 802.1s - Maps multiple VLANs into same spanning-tree instance to save processing on switch
- **Rapid PVST+** - Cisco's version of RSTP that also uses PVST+ and provides separate instance of 802.1w per VLAN - fast convergence times and optimal traffic flow - requires most CPU and memory of all 

##### Basic Operations 
- Root Bridge - bridge with the lowest Bridge ID
- Non-Root Bridge - all bridges that aren't the root bridge, exchange BPDUs with all other bridges and update STP topology database on all switches
- Designated Port - one that’s been determined to have the best (lowest) cost to get to on a given network segment, always in forwarding state
- Non-Designated Port - one with higher cost that designated port, put in blocking, or discarding mode
- Bridge ID - how STP keeps track of all switches in the network, determined by combination of bridge priority (32,768 default on all Cisco switches) and base MAC address
- Port Cost - determines best path when multiple links are used between 2 switches, cost of a link is determined by bandwidth of a link, path cost is deciding factor used by every bridge to find most efficient path to root bridge 

##### Port States 
-	Disabled – port in administratively disabled state doesn’t participate in frame forwarding or STP
-	Blocking – won’t forward frames – just listens to BPDUs, all ports are in blocking state by default when switch is powered on
-	Listening – listens to BPDUs to make sure no loops occur on network before passing data frame, prepares to froward data frames without populating MAC table
-	Learning – listens to BPDUs and learns all paths in switched network, populates MAC table but doesn’t forward data frames. Forward delay = 15 seconds’ default 
-	Forwarding – port sends and receives all data frames on bridged port, if port designated or root port at the end of learning state, it would enter forwarding 


##### Port Cost Based on Speed of Link 
|  Speed  | Cost |
|--------- | -----|
| 10 Mbps  |  100 |
| 100 Mbps |  19  |
| 1,000 Mbps |  4 |
| 10,000 Mbps | 2 |

##### To Configure STP Mode:
```
#spanning-tree mode [mst | psvt | rapid-pvst]
```

### PortFast
-	BPDU – data message forwarded across LAN to detect loops in spanning tree topology – contains information about ports, switches, port priority, and addresses 
-	Enables switch to instantaneously transition from blocking to forwarding state immediately bypassing listening/learning state
-	Highly recommended only on non-trunking access ports

##### To configure on access switch port interface:
```
#int f0/10
#spanning-tree portfast 
#spanning-tree portfast default 
```

##### To configure BPDU guard
```
#int f0/1
#spanning-tree portfast
#spanning-tree bpduguard enable
#spanning-tree portfast bpduguard default 
```

