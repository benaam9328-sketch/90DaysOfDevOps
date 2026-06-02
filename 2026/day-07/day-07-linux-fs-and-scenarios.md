### Part 1: Linux File System Hierarchy (30 minutes)

Document the purpose of these **essential** directories:

**Core Directories (Must Know):**
- `/` (root) - The starting point of everything -it contains all system files
- `/home` - User home directories -use when issue is user specific
- `/root` - Root user's home directory- for root access files
- `/etc` - Configuration files - for changing system conf
- `/var/log` - Log files (very important for DevOps!) - looking log of application and system
- `/tmp` - Temporary files - temp storage 

**Additional Directories (Good to Know):**
- `/bin` - Essential command binaries -system cmds are failing
- `/usr/bin` - User command binaries- system cmd working application level cmd failing
- `/opt` - Optional/third-party applications - troubleshoot third party application.

**Hands-on task:**
```bash
# Find the largest log file in /var/log
du -sh /var/log/* 2>/dev/null | sort -h | tail -5

root@ip-172-31-34-19:/var/log# du -sh /var/log/* 2>/dev/null | sort -n
0       /var/log/README
0       /var/log/apport.log
0       /var/log/btmp
0       /var/log/btmp.1
0       /var/log/ubuntu-advantage-apt-hook.log
2.8M    /var/log/sysstat
4.0K    /var/log/alternatives.log
4.0K    /var/log/chrony
4.0K    /var/log/dist-upgrade
4.0K    /var/log/dpkg.log
4.0K    /var/log/landscape
4.0K    /var/log/private
8.0K    /var/log/cloud-init-output.log
8.0K    /var/log/lastlog
8.0K    /var/log/wtmp
12K     /var/log/nginx
16K     /var/log/alternatives.log.1
16K     /var/log/dmesg.1.gz
16K     /var/log/unattended-upgrades
25M     /var/log/journal
48K     /var/log/apt
52K     /var/log/dmesg
52K     /var/log/dmesg.0
64K     /var/log/kern.log
72K     /var/log/dpkg.log.1
140K    /var/log/kern.log.1
280K    /var/log/auth.log
308K    /var/log/amazon
412K    /var/log/cloud-init.log
488K    /var/log/syslog
496K    /var/log/auth.log.1
904K    /var/log/syslog.1
------------------------------------------------
# Look at a config file in /etc
cat /etc/hostname
ip-172-31-34-19
-------------------------------------------------
# Check your home directory
ls -la ~
total 52
drwx------  8 root root 4096 May 31 05:34 .
drwxr-xr-x 19 root root 4096 Jun  2 14:58 ..
-rw-------  1 root root 1582 May 31 06:32 .bash_history
-rw-r--r--  1 root root 3106 Apr 20 08:46 .bashrc
drwx------  2 root root 4096 May 24 07:09 .cache
-rw-r--r--  1 root root   63 May 31 04:37 .gitconfig
drwxr-xr-x  3 root root 4096 May 31 04:45 .local
-rw-r--r--  1 root root  132 Apr 20 08:46 .profile
drwx------  2 root root 4096 May 31 05:37 .ssh
-rw-------  1 root root 2305 May 31 05:34 .viminfo
drwxr-xr-x  3 root root 4096 May 31 04:48 Github
drwxr-xr-x  3 root root 4096 May 31 05:36 Shell-scripts
drwx------  3 root root 4096 May 23 04:27 snap


```
---
