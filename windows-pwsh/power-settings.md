## How To: Modify power settings via Powershell

Tested on:
  * Windows 11
  * Windows Server 2022 Standard (not a domain controller)

---

To disable standby:
```pwsh
powercfg -change -standby-timeout-ac 0
powercfg -change -standby-timeout-dc 0
```

To disable hibernation:
```pwsh
powercfg -change -hibernate-timeout-ac 0
powercfg -change -hibernate-timeout-dc 0
```
