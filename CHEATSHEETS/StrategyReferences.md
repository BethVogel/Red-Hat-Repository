```
given 1 IP address:
route network and enum (NIC1 visible)
say FTP, SSH and 80 open
enum for subdomains or portals
Try and get initial access via OSINT breached creds, password reuse, brute force
lockout policy
say webpage is externally facing
attempt common website vulns - IDOR etc
look at what is running via wappalyzer or builtwith for potential vuls, potential information disclosure
manipulate a password reset or brute force via burp
add a reverse shell via webpage template
get a shell and assume linux box
	- escalate access to get root via SUID or cron task.
	- dump any hashes and crack or pass via cme
create and add SSH keys to FTP and ssh into root account with rsa keys
ssh into computer - map network and enum, ping ips (NIC1 and NIC2 visible)
proxychain to get open ports on remaining computers
cme accross all with hashes and passwords to continue to collect logins
potentially run responder when ready to be 'louder'
move laterally onto computers and enumerate more
attempt kerberos domain controller
smb into other computers and create a reverse shell if cant ssh
enable RDP on windows comp
map AV/firewall and disable if needed
windows priv esc on remaining comps 
start quiet with version manual exploits or powershell enum
potential unquoted service paths, vuln applications installed, files saved with passwords
Get noisy:
Run responder, mimikatz, win/linPEAS, metasploit, windows-exploit-suggester
run vuln scans to capture unpatching and other vulns: Nikto, nessus, etc

COMP1 other NIC2, 
SSH - 
	- ssh into computer
	- check network, ping alive IPs
	- dual NIC - pivot into nic2 and keep the port open
	- proxychain scan for others connected 
	- proxy into other computers through open ports
	- get a shell through smb on another comp and get RDP on it
	- find the domain and attempt a kerberose
	- create keys and ssh into other computers 
	- can just use for password spray and cme before moving laterally domain controller

COMP2 NIC2 - 
8080
	- ie access firefox for one with open 80 ports
		○ burp to intercept a sign-in request
		○ send to intruter for checking
	- try password reset, IDOR 
	- assume this is a linux box
	- get a webshell and upgrade
	- find SUID GTFO and get root or a cron task
	

COMP3 domain
RDP
	- access rdp from another computer
	- download mimikatz to get loud
	- run responder
	- create account

windows AD priv esc
	- potential unquoted service path
	- kerberose/crackmapexec
	
disable windows AV and put mimikatz or responder to see how loud can get

```


- If have: 
```
port 80
going to look for a 
port 21 FTP 
port 22 ssh
80 for creds, then ssh

80:
	- enum for subdomains and portals
	- breached creds
	- wappalyzer/built with - lockout policy 
	- common website vulns - IDOR etc
	- information disclosure
	- brute force/password reset/burp
	- low level access via file upload to portal
	- linux box:
		○ priv esc to get root
			§ SUID, caps, GTFObins
			§ cron task
			§ cme dump hash and pass

22:
		○ create and add rsa keys
		○ connect via ssh
		○ map network and pivot into another NIC
		○ ping ips and nmap via proxychains
		○ cme across all with hashes and passwords
		○ responder potentially
		○ move laterally and enumerate
		○ kerberoast domain controller
	
SMB:
	- kerbrute credentials
	- signing enabled but not required 
		○ impacket smb relay

enable RDP 
map AV/firewall and disable
windows priv esc
quiet with manual exploits or powershell enum
unquoted service paths, vuln in applications
saved passwords
get noisy:
responder, mimikatz, win/linpeas, metasploit

run vuln scans to capture patching needs and other vulns: Nikto, nessus, etc
```
