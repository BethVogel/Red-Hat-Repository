## General Notes
- searchsploit for version
- default credentials
- brute or bust, typically will be using an exploit in something else to log into this and get lower level shell
  - `ssh 10.0.0.12` try without password
  - `hydra -l root -P /usr/share/wordlist/metasploit/unix_passwords.txt ssh://10.0.0.12:22 -t 4 -V`
  - `hydra -l root -P /usr/share/wordlists/rockyou.txt ssh://{ip} -t 4 -V`
  - `ffuf -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt:FUZZ -u [ssh://10.10.10.10/FUZZ](ssh://10.10.10.10/FUZZ)`
- SSH keys
  - `ssh -i id_rsa username@10.10.10.10`
- when connecting to ssh do ss -tulpn to see what socket connections are running
- SSH is great for pivoting
  - Port Forwarding
    - If want to connect to a webpage that dont have access to but have access to another comp on its network
      - `ssh -L 800:10.10.10.10:80 user@10.10.10.5 -fN`
    - navigate to `localhost:8000`
      - Example assumes SSH access to 10.10.10.5 and webserver on 10.10.10.10
    - `ssh -L 8000:10.10.10.10 user@10.0.0.12 -fN`
      - above example assumes we have access 10.0.0.12 and there is a webserver running on 10.10.10.10
      - fN backgrounds the shell and indicates just set up connection and not exectute a command
  - Proxy
    - `ssh -D 8000 user@target.thm -fN`
    - Can also use 1337 as a port. It will open up a port 1337 on localhost to act as a proxy and send data through into the protected network. This is used with proxychains.
      - Make sure proxychains config file set up correctly


*NOTE: See Pivoting page for more information*
