#### Port strategy quick wins
```
assuming linux:
80: http/https
	- enum for subdomains and portals
	- breached creds
	- wappalyzer/built with - lockout policy 
		○ exploits for versions
	- common website vulns - IDOR etc
	- information disclosure
	- brute force/password reset/burp
	- low level access via file upload to portal
	- linux box:
		○ priv esc to get root
			§ sudo -l
			§ SUID, caps, GTFObins
			§ cron task
		○ /etc/shadow
		○ look for ssh keys
		○ can put files via FTP as needed for scans

22: ssh
		○ connect via ssh id_rsa keys
		○ map network and pivot into another NIC
		○ ping ips and nmap via proxychains
		○ cme across all with hashes and passwords
		○ responder potentially
		○ move laterally and enumerate
		○ kerberoast domain controller
```

```
assuming windows:
445: SMB
88: Kerberos
389: ldap
		○ smb enum, file transfer
    ○ kerbrute credentials
		○ signing enabled but not required 
		○ impacket smb relay

3389:
		○ enable RDP 
		○ map AV/firewall and disable
		○ windows priv esc
		○ quiet with manual exploits or powershell enum
		○ unquoted service paths, vuln in applications
		○ saved passwords

get noisy:
responder, mimikatz, win/linpeas, metasploit
run vuln scans to capture patching needs and other vulns: Nikto, nessus, etc
```
