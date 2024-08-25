## How To: Find Service Tag / Serial Number 

Tested on:

  * Windows 11
  * Windows Server 2022 Standard (not a domain controller)

---

1. Run the command.
```pwsh
(Get-WmiObject -Class Win32_BIOS).SerialNumber
```

