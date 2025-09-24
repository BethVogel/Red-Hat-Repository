## Linux PE

**Strategy**
- Checklists - payloadsallthethings, hacktricks
- Enum Scripts - run tools
- Kernel Exploits - vulnerabilities in an unpatched system
- Vulnerable Software - check what is installed
- User Privileges - sudo, suid, windows token privileges
- Scheduled tasks - cron jobs or windows scheduled tasks
- Exposed Credentials - review enum scripts, configuration files, logs, bash_history or PSReadLine in windows
- SSH Keys


**Kernal/file details**
  - network: route, dns
  - System and user info
    - uid/gid, root accounts, password policies and hash storage methods
    - umask value
    - /etc/passwd and /etc/shadow
    - default uids (0, 1000, 1001 etc) extract details
    - user history (bash_history, .nano_history, .mysql_history)
    - ssh checks
  - Files with passwords:
    - `grep --color=auto -rnw '/' -ie "PASSWORD" --color=always 2> /dev/null`
    - `find . -type f -exec grep -i -I "PASSWORD" {} /dev/null \;`
  - Sensitive files
    - `find / -name authorized_keys 2> /dev/null`
    - `find / -name id_rsa 2> /dev/null`

### GTFO Bins
**SUID**
  - `find / -perm -4000 -type f -exec ls -la {} 2>/dev/null \;`
  - `find / -uid 0 -perm -4000 -type f 2>/dev/null`

**Capabilities**
  - `getcap`
    
**NOPASSWD**
  - `sudo -l`

**Cron jobs**
```
/etc/init.d
/etc/cron*
/etc/crontab
/etc/cron.allow
/etc/cron.d 
/etc/cron.deny
/etc/cron.daily
/etc/cron.hourly
/etc/cron.monthly
/etc/cron.weekly
/etc/sudoers
/etc/exports
/etc/anacrontab
/var/spool/cron
/var/spool/cron/crontabs/root

crontab -l
ls -alh /var/spool/cron;
ls -al /etc/ | grep cron
ls -al /etc/cron*
cat /etc/cron*
cat /etc/at.allow
cat /etc/at.deny
cat /etc/cron.allow
cat /etc/cron.deny*
```

