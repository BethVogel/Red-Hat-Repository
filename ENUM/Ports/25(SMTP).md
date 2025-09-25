#### SMTP
- Used for emails
- potential enum

- nmap
  - `nmap 10.10.10.11 --script=smtp* -p 25`
  - `nmap --script=smtp-commands,smtp-enum-users,smtp-vuln-cve2010-4344,smtp-vuln-cve2011-1720,smtp-vuln-cve2011-1764 -p 25 $ip`
 
  - user enum:
    - `smtp-user-enum -M VRFY -U /usr/share/wordlists/metasploit/unix_users.txt -t $ip`
- `telnet $ip 25`
