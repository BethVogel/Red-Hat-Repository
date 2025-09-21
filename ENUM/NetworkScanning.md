`netdiscover -r {ip}/24`
`arp-scan -l`
`arp-a`
- windows or linux, shows ARP cache of the machine (hosts target interacted with recently)

`cat /etc/hosts`
or 
`C:\Windows\System32\drivers\etc\hosts`
also `ipconfig /all`
- check local dns services to see if they are misconfigured
- for linux it is `nmcli dev show` or in the `/etc/resolv.confi`
Ping from the terminal if need to get current

MAC address for type of device
