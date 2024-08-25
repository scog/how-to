## How To: Reset Local User Password using Powershell

Tested on:

  * Windows 11
  * Windows Server 2022 Standard (not a domain controller)

---

1. Set your username and password variables.
```pwsh
$Username = "<USERNAME>"
$NewPassword = "<PASSWORD>"
```

2. Run the commands:
```pwsh
$User = Get-LocalUser -Name $Username
$User | Set-LocalUser -Password (ConvertTo-SecureString -AsPlainText $NewPassword -Force)
$User | Set-LocalUser -PasswordNeverExpires $true
```
