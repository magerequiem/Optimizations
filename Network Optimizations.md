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

```
# Advanced UDP Network Optimizations for Gaming

This guide contains low-level Windows registry tweaks, network adapter configurations, and router settings optimized specifically for User Datagram Protocol (UDP) traffic. These settings reduce packet processing latency, minimize jitter, and prioritize real-time gaming data (such as VALORANT, CS2, and Apex Legends).

---

## 🛠️ 1. Windows Registry Tweaks

These adjustments modify the Windows Ancillary Function Driver (AFD) and system profile to eliminate built-in network throttling and packet-queuing delays.

### A. Disable Network Throttling
1. Press `Win + R`, type `regedit`, and hit **Enter**.
2. Navigate to: `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Multimedia\SystemProfile`
3. Locate **NetworkThrottlingIndex**. Double-click it, set the Base to **Hexadecimal**, and set the Value data to `ffffffff`.
4. Locate **SystemResponsiveness**. Double-click it, set the Base to **Hexadecimal**, and set the Value data to `0`.

### B. Optimize UDP Datagram Buffering
1. Navigate to: `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\AFD\Parameters`
   *(If the `Parameters` key does not exist, right-click `AFD` -> `New` -> `Key` and name it `Parameters`)*.
2. Inside `Parameters`, right-click the empty right pane and select **New** -> **DWORD (32-bit) Value**. Create the following two entries:
   * **`FastSendDatagramThreshold`**: Set Base to **Hexadecimal** and Value data to `4000`. (Allows larger UDP packets to bypass standard buffering).
   * **`IgnorePushBitOnReceive`**: Set Base to **Hexadecimal** and Value data to `1`. (Forces the OS to process incoming UDP packets instantly instead of waiting for a buffer signal).
3. Restart your PC to apply all registry changes.

---

## ⚙️ 2. Network Adapter Properties

These configurations disable power-saving states and packet-bundling features on your network interface card (NIC), forcing instant packet transmission.

1. Press `Win + X` and select **Device Manager**.
2. Expand **Network adapters**, right-click your primary Ethernet Controller, and select **Properties**.
3. Go to the **Advanced** tab and configure the following settings:

* **UDP Checksum Offload (IPv4 & IPv6)** ➡️ `Disabled`
  * *Why:* Shifts packet verification to the CPU, preventing budget network chips from delaying UDP data packets.
* **Large Send Offload v2 (IPv4 & IPv6)** ➡️ `Disabled`
  * *Why:* Stops Windows from aggregating small packets into larger blocks, forcing real-time data out instantly.
* **Packet Coalescing** ➡️ `Disabled`
  * *Why:* Prevents the network card from holding back incoming packets to process them in groups.
* **Interrupt Moderation** ➡️ `Disabled`
  * *Why:* Forces the system to handle packets immediately upon arrival rather than queuing them (increases CPU usage by <1%).
* **Energy Efficient Ethernet / Green Ethernet** ➡️ `Disabled`
  * *Why:* Stops the network adapter from entering low-power states that cause sudden latency spikes.

---

## 🌐 3. Network Routing & DNS Optimization

Standard ISP DNS nodes often use inefficient routing maps. Shifting to gaming-optimized DNS layers ensures faster lookups.

1. Press `Win + R`, type `ncpa.cpl`, and hit **Enter**.
2. Right-click your active **Ethernet adapter** -> **Properties**.
3. Double-click **Internet Protocol Version 4 (TCP/IPv4)**.
4. Select **"Use the following DNS server addresses"** and input the Cloudflare high-performance nodes:
   * **Preferred DNS server:** `1.1.1.1`
   * **Alternate DNS server:** `1.0.0.1`
5. Open **Command Prompt (Admin)** and flush your old routing tables with:
   ```cmd
   ipconfig /flushdns
   

---

## 📡 4. Router Quality of Service (QoS)

Prioritize your gaming packets at the hardware gateway layer so household background traffic cannot cause queue delays.

1. Log into your router's administration panel (typically `192.168.1.1` or `192.168.0.1`).
2. Locate the **QoS (Quality of Service)** or **Traffic Prioritization** settings menu.
3. Create a rule to prioritize traffic based on your gaming device's MAC/IP address or specific application ports.
4. For games like **VALORANT**, prioritize the following core gameplay ports and set their priority level to **Highest** or **Real-Time**:
   * **UDP Range:** `7000 - 8000`

---

## ⚠️ Disclaimer & Reverting

These tweaks are fully safe, will not trigger anti-cheat software (like Vanguard or EAC), and do not modify game files. 

### How to Revert:
* **Registry:** Delete the created keys under `AFD\Parameters` and reset `NetworkThrottlingIndex` to `a`.
* **Network Adapter:** Change all advanced adapter settings back to `Enabled` or `Operating System Determined`.
```
