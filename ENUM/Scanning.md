## NMAP
`nmap -T4 -p- -A 10.0.0.0`
		- T4 is speed, -p- scanning all ports, -A scanning everything
    - sn: ping scan sweaps an entire network
- Pn: treat them all like they are online
`nmap -T4 -p 1-1000 -A 10.0.0.0`
		- first 1000 ports

Vuln Options:
`nmap -oA nmap-vuln -Pn -script vuln -p 80,135,139,445,3389 10.10.220.181`


HTTP nmap enum:
`nmap -script http-enum.nse 0.0.0.0`

## Vulnerability scanning
	- metasploit
	- searchsploit
	- Nessus
	- Nikto
	- linpeas
	- winpeas
	- windows-exploit-suggester
	- linux-exploit-suggester
	- enum4linux -a IP 
		- can enumer for other domain information
