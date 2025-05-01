## How To: Get list of local Windows accounts in JSON format via Powershell

Tested on:
  * Windows 11
  * Windows Server 2022 Standard (not a domain controller)

---

Run the command:
```pwsh
$localUsers = Get-WmiObject -Class Win32_UserAccount -Filter "LocalAccount='True'"
$localUsers | Select-Object -Property Name | ConvertTo-Json
```
