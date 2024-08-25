## How To: Enable Windows Remote Desktop Protocol (RDP) via Powershell

Tested on:
  * Windows 11
  * Windows Server 2022 Standard (not a domain controller)

---

1. Change value in registry settings:
```pwsh
Set-ItemProperty -Path 'HKLM:\System\CurrentControlSet\Control\Terminal Server' -Name "fDenyTSConnections" -Value 0
```

2. Allow RDP on the firewall:
```pwsh
Enable-NetFirewallRule -DisplayGroup "Remote Desktop"
```

3. Restart the service
```pwsh
Restart-Service -Name TermService -Force
```

## Optional:

To disable Network-level Authentication
```pwsh
#
# Warning:
# Do not recommend this setting on a Domain-enabled PC or Server
#
Set-ItemProperty -Path 'HKLM:\System\CurrentControlSet\Control\Terminal Server\WinStations\RDP-Tcp' -Name UserAuthentication -Value 0

```
