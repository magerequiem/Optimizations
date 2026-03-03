# __Registory Tweaks__
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
