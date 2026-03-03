# __NVIDIA Control Panel Settings__

```yaml
Image Sharpening = Sharpening Off 
Ambient Occlusion = Not supported for this application
Anisotropic filtering = Application-controlled
Antialiasing - FXAA = Off
Antialiasing - Gamma correction = Off
Antialiasing - Mode = Application-controlled
Antialiasing - Setting = Application Controlled
Antialiasing - Transparency = Off
Background Application Max Frame Rate = Off
CUDA - GPUs = All
CUDA - Sysmem Fallback Policy = Driver Default
Low Latency Mode = Ultra
Max Frame Rate = Off
Multi-Frame Sampled AA (MFAA) = Off
OpenGL GDI compatibility = Prefer performance
OpenGL rendering GPU = Your GPU
Power management mode = Prefer maximum performance
Texture filtering - Anisotropic sample option = On
Texture filtering - Negative LOD bias = Allow 
Texture filtering - Quality = High performance
Texture filtering - Trilinear optimization = Off
Threaded optimization = On
Triple buffering = Off
Vertical sync = Off 
```
# __Registory tweaks__
## Registry Directory for CPU and GPU Priority Tweaks
**Directory:**
```ml
Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Multimedia\SystemProfile\Tasks\Games
```
**Settings:  **
```yaml
1. GPU Priority = Decimal - 8
2. Priority = Decimal - 6
3. Scheduling Category = High
4. SFIO Priority = High
```
## Registry Directory for NetworkThrottlingIndex & SystemResponsiveness
**Directory:**
```ml
Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Multimedia\SystemProfile
```
**Settings:**
```yaml
1. NetworkThrottlingIndex = Hexadecimal - ffffffff
2. SystemResponsiveness = Decimal 14
```

# RISKY!!!!!!!
## Registry Directory for Win32PrioritySeparation
**Directory:**
```ml
Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\PriorityControl
```
**Settings:**
```yaml
1. Win32PrioritySeparation = Decimal - 38
```
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
