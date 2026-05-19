------Pocess Management--------
1.ps -aux  
2.ps -ef
3.pkill nginix
4.kill pid
5.kill -9 pid  //forcefully kill the process
6.pgrep nginx //find process of nginx
7.free -h
8.jobs //show bg job in current shell
9.bg
10.fg
11.nohop cmd &

------------File Commands---------------------------
1.cp src dest
2.mv src dest
3.touch file.txt
4.mkdir folder
5.grep "text" demo.txt  //search text from file
6.rm file.txt
7.rm -rf dir //recursive remove forcefully
8.find /path -name file.name //find a purticular file
9.chmod 775
10.chown user:group
11. tail -n10 file.txt

-------------Networking Commands-----------------------
1.ping google.com
2.traceroute google.com
3.nslookup google.com
4.ss -tulnp 
5.dig google.com

------Other useful system commnds------
1. usname -a //kernel ,sysetem info
2. shutdown now
3. reboot
