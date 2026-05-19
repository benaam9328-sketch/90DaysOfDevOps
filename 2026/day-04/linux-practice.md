----Process Commands------
1.ps -ef (show every running process in full format)
root@bcf73052a43f:~# ps -ef
UID        PID  PPID  C STIME TTY          TIME CMD
root         1     0  0 21:45 pts/0    00:00:00 /bin/bash
root        58     1  0 23:05 ?        00:00:00 nginx: master process /usr/sbin/nginx
www-data    59    58  0 23:05 ?        00:00:00 nginx: worker process
www-data    60    58  0 23:05 ?        00:00:00 nginx: worker process
www-data    61    58  0 23:05 ?        00:00:00 nginx: worker process
www-data    62    58  0 23:05 ?        00:00:00 nginx: worker process
www-data    63    58  0 23:05 ?        00:00:00 nginx: worker process
www-data    64    58  0 23:05 ?        00:00:00 nginx: worker process
www-data    65    58  0 23:05 ?        00:00:00 nginx: worker process
www-data    66    58  0 23:05 ?        00:00:00 nginx: worker process
root        72     1  0 23:06 pts/0    00:00:00 ps -ef

2.Top
top - 23:12:56 up  1:32,  0 users,  load average: 0.00, 0.00, 0.00
Tasks:  11 total,   1 running,  10 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.4 us,  0.1 sy,  0.0 ni, 99.4 id,  0.0 wa,  0.0 hi,  0.1 si,  0.0 st
MiB Mem :   3798.1 total,   2874.7 free,    681.4 used,    375.6 buff/cache
MiB Swap:   1024.0 total,   1024.0 free,      0.0 used.   3116.7 avail Mem

  PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND                                                                    
   74 root      20   0    7716   5240   3216 R   0.3   0.1   0:00.01 top                                                                        
    1 root      20   0    4768   4156   3528 S   0.0   0.1   0:00.43 bash
   58 root      20   0   14824   2412    936 S   0.0   0.1   0:00.01 nginx
   59 www-data  20   0   15192   3532   1724 S   0.0   0.1   0:00.00 nginx
   60 www-data  20   0   15192   3532   1724 S   0.0   0.1   0:00.00 nginx
   61 www-data  20   0   15192   3532   1724 S   0.0   0.1   0:00.00 nginx
   62 www-data  20   0   15192   3532   1724 S   0.0   0.1   0:00.00 nginx
   63 www-data  20   0   15192   3528   1720 S   0.0   0.1   0:00.00 nginx
   64 www-data  20   0   15192   3532   1724 S   0.0   0.1   0:00.00 nginx

   ----------System command-----------------------
   1.systemctl status nginx
   active running
   2.systemctl restart nginx
   3.systemctl stop nginx
   --------Log command---------------
   1.journalctl -u nginx
   2.crontab -l
   65 www-data  20   0   15192   3532   1724 S   0.0   0.1   0:00.00 nginx
   66 www-data  20   0   15192   3428   1620 S   0.0   0.1   0:00.00 nginx
