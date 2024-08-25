
# How To: Apply Windows License via Powershell

Tested on:

  * Windows Server 2022 Standard (not a domain controller)

---

1. Set you license key & edition variable:
```pwsh
$MyLicenseKey = "XXXXX-XXXXX-XXXXX-XXXXX-XXXXX"
$MyEdition = "ServerStandard"
```

2. Apply the license.
```pwsh
  DISM /online /Set-Edition:$MyEdition /ProductKey:$MyLicenseKey /AcceptEula
```
3. It will prompt you to reboot (possibly twice)
