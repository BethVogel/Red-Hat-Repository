#### Creating an account
`net user name Username12345678* /add /Y`
`net localgroup administrators name /add`
`net localgroup "Remote Desktop Users" name /add` #access RDP
`net localgroup "Backup Operators" name /add` #full acceess to files
`net group "Domain Admins" name /add /domain` 
`net user name /ACTIVE:YES /domain` #enables domain user account
