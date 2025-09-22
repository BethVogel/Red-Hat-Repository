## Network scanning

- `netdiscover -r [range]/24`
- `arp-scan -l [range]`
- `arp-a`
  - windows or linux, shows ARP cache of the machine (hosts target interacted with recently)
- `cat /etc/hosts` or `C:\Windows\System32\drivers\etc\hosts`
- `ipconfig /all`
  - check local dns services to see if they are misconfigured or not set up
  - for linux it is `nmcli dev show` or in the `/etc/resolv.confi`
- Ping from the terminal if need to get current IP
- MAC address for type of device
