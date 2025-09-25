## Spawning TTY Shell
```
python -c 'import pty;pty.spawn("/bin/bash")'
export TERM=xterm
Ctrl + Z
stty raw -echo; fg
export TERM=xterm
```
#### Other options:
```
echo os.system('/bin/bash')
/bin/sh -i
perl -e 'exec "/bin/sh";'
perl: exec "/bin/sh"
ruby: exec "/bin/sh"
lua: os.execute('/bin/sh')
```
