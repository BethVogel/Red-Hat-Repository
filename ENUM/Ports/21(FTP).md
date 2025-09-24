### General Notes:
- FTP by itself not typically exploitable but versions can be.
- use binary instaed of .aspx
- `ftp 10.10.10.10`
  - username: Anonymous
- *Brute force*
  - `hydra -l root -P /usr/share/wordlists/rockyou.txt ftp://{ip} -t 4 -V`
- search for potential ssh keys
- use with 80 to 'put' and navigate to file
