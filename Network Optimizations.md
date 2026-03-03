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
