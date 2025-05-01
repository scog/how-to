## How To: Enable and configure Windows Time Service (w32tm) via Powershell

Tested on:
  * Windows 11
  * Windows Server 2022 Standard (not a domain controller)

---

To enable time service and configure Central Timezone:
```pwsh
w32tm.exe /config /syncfromflags:manual /manualpeerlist:"time.windows.com"
tzutil.exe /s "Central Time Standard"
Start-Service W32Time
Set-Service -Name W32Time -StartupType Automatic
net stop w32time
Start-Sleep -Seconds 5
net start w32time
w32tm.exe /resync
```
