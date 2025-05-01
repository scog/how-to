## How To: Modify audit policies via Powershell

Tested on:
  * Windows 11
  * Windows Server 2022 Standard (not a domain controller)

---

To enable logging for all authentication attempts:
```pwsh
auditpol /set /category:"Logon/Logoff" /subcategory:"Logon" /success:enable /failure:enable
```
