# __Network Optimizations__

## Step 1 - Cmd ping check

**1. Cmds**```java
Wind + R > cmd > ok
Cmds :
ping 1.1.1.1
ping 8.8.8.8
```
**2. Example :**```yaml

C:\Users\nonam>ping 1.1.1.1

Pinging 1.1.1.1 with 32 bytes of data:
Reply from 1.1.1.1: bytes=32 time=35ms TTL=52
Reply from 1.1.1.1: bytes=32 time=32ms TTL=52
Reply from 1.1.1.1: bytes=32 time=30ms TTL=52
Reply from 1.1.1.1: bytes=32 time=33ms TTL=52

Ping statistics for 1.1.1.1:
    Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
Approximate round trip times in milli-seconds:
    Minimum = 30ms, Maximum = 35ms, Average = 32ms

C:\Users\nonam>ping 8.8.8.8

Pinging 8.8.8.8 with 32 bytes of data:
Reply from 8.8.8.8: bytes=32 time=39ms TTL=111
Reply from 8.8.8.8: bytes=32 time=37ms TTL=111
Reply from 8.8.8.8: bytes=32 time=38ms TTL=111
Reply from 8.8.8.8: bytes=32 time=35ms TTL=111

Ping statistics for 8.8.8.8:
    Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
Approximate round trip times in milli-seconds:
    Minimum = 35ms, Maximum = 39ms, Average = 37ms

```
## Step 2 - DNS Configuration
1. Settings App (Wind + I)

**Path :**```ml
Network & Internet > Advanced Network Settings
Choose = Wifi/Ethernet > More Adaptor Options - edit
Tab = Networking
```**Configuration:**
```yaml
if :
Client for Microsoft networks = :heavy_check_mark:
Internet Protocol Version 4 = :heavy_check_mark:
Internet Protocol Version 6 = :heavy_check_mark:

else :
Uncheck

Internet Protocol Version 4 > Properties
Tab = General > 
Preferred DNS Server = 1.1.1.1 / 8.8.8.8
Alternate DNS Server = 1.0.0.1 / 8.8.4.4

Note : 
if Preferred DNS Server = 1.1.1.1 then Alternate DNS Server = 1.0.0.1 
else Preferred DNS Server = 8.8.8.8 then Alternate DNS Server = 8.8.4.4

Tab = Networking
Configure...
Tab = Power Management
Uncheck = "all"

Tab = Advanced 
Adaptive Inter-Frame Spacing = Disabled
ARP Offload = Disabled
Enable PME = Disabled
Energy Effcient Ethernet = Off
Flow Control = Disabled
Gigabit Master Slave Mode = Auto Detect
Gigaphit PHY Mode = Auto Detect
Interupt Moderation = Disabled
Interrupt Moderation Rate = Off
Ipv4 Checksum Offload = Disabled
Jumbo Packet = Disabled
Large Send Offload V2(Ipv4) = Disabled
Large Send Offload V2(Ipv6) = Disabled
Logically Administered Adress = Not Present
Log Link State Event = Disabled 
Maximum Number of RSS Queues = 2 Queuse
NS Offload = Disabled
Packet Priority & VLAN = (sec opt) Enabled
PTP Hardware TimeStamp = Disabled
Recieve Buffers = 2048 / 1024 
Recieve Side Scaling = Disabled
Reduce Speed on Power Down = Disabled
Software TimeStamps = Disabled 
Speed & Duplex = Auto Negotiation / Highest Full Duplex
TCP Checksum Offload(Ipv4) = Disabled
TCP Checksum Offload(Ipv6) = Disabled
Transmit Buffers = 2048 if Recieve buffers same else 2x Receive Buffers
Rest all Disabled....
```
