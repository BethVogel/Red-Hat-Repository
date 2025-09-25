```python
#!/bin/python3

import socket
#socket will connect to a port

HOST = '127.0.0.1' #localhost
PORT = 1234

s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
s.connect((HOST, PORT))
#establishes connection between host and port

# must run listener to connect "nc -nvlp 7777"

```
