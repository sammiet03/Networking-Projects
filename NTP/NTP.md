### NTP
- Network Time Protocol
- Port 123
- Synchronizes clocks of computer systems over packet-switched, variable-latency data networks 

```
#service timestamps log datetime msec
#ntp server 172.16.10.1 version 4

To check NTP Configuration
#sh ntp status
#sh ntp associations
```
