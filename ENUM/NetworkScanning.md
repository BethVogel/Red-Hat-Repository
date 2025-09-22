## Network scanning

- port scanning, vuln scanning, network mapping
- MAC address - type of device
- `netdiscover -r [range]/24`
- `arp-scan -l [range]`
  - ARP cache of the machine (hosts target interacted with recently)
- `cat /etc/hosts` or `C:\Windows\System32\drivers\etc\hosts`
- check for local dns services to see if they are misconfigured or not set up
  - Windows
    - `ipconfig /all`
  - Linux
    - `nmcli dev show`
    - `/etc/resolv.confi`
    - `ip a`
- Ping from the terminal if need to get current IP
