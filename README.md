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
