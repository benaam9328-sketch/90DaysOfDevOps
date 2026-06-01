OSI - 7 layers, no overlapping, theoritical
TCP/IP- 4layers, Overlapping, Practical 

-------------------------------------------

Where IP, TCP/UDP, HTTP/HTTPS, DNS sit in the stack
--------------------------------------------------------

IP- Network
TCP/UDP- Transport
HTTP/HTTPS- Application
DNS- Application

----------------------------------------------------------
One real example: “curl https://example.com = App layer over TCP over IP”
---------------------------------------------------------------------------
wwww.example.com-->application (https and DNS)----->Transport layer(TCP)---->Network layer(IP)

Identity: hostname -I (or ip addr show) — note your IP.
172.31.34.19 172.17.0.1
Reachability: ping <target> — mention latency and packet loss.
ubuntu@ip-172-31-34-19:~$ ping 8.8.8.8
PING 8.8.8.8 (8.8.8.8) 56(84) bytes of data.
64 bytes from 8.8.8.8: icmp_seq=1 ttl=116 time=9.01 ms
64 bytes from 8.8.8.8: icmp_seq=2 ttl=116 time=8.93 ms
64 bytes from 8.8.8.8: icmp_seq=3 ttl=116 time=8.90 ms
64 bytes from 8.8.8.8: icmp_seq=4 ttl=116 time=8.95 ms
64 bytes from 8.8.8.8: icmp_seq=5 ttl=116 time=8.90 ms
64 bytes from 8.8.8.8: icmp_seq=6 ttl=116 time=8.91 ms
64 bytes from 8.8.8.8: icmp_seq=7 ttl=116 time=8.88 ms
64 bytes from 8.8.8.8: icmp_seq=8 ttl=116 time=8.92 ms
64 bytes from 8.8.8.8: icmp_seq=9 ttl=116 time=8.89 ms
64 bytes from 8.8.8.8: icmp_seq=10 ttl=116 time=8.88 ms
64 bytes from 8.8.8.8: icmp_seq=11 ttl=116 time=8.98 ms
64 bytes from 8.8.8.8: icmp_seq=12 ttl=116 time=8.99 ms
64 bytes from 8.8.8.8: icmp_seq=13 ttl=116 time=8.88 ms
64 bytes from 8.8.8.8: icmp_seq=14 ttl=116 time=8.95 ms
64 bytes from 8.8.8.8: icmp_seq=15 ttl=116 time=8.90 ms
^C
--- 8.8.8.8 ping statistics ---
15 packets transmitted, 15 received, 0% packet loss, time 14021ms
rtt min/avg/max/mdev = 8.877/8.924/9.005/0.039 ms

Path: traceroute <target> (or tracepath) — note any long hops/timeouts.
yes timeout on www.yamaha-motor-india.com
traceroute to www.google.com (142.251.157.119), 64 hops max
  1   242.4.178.65  8.832ms  8.595ms  8.506ms 
  2   *  *  * 
  3   151.148.9.135  9.102ms  9.096ms  9.108ms 
  4   142.251.157.119  7.843ms  7.867ms  7.826ms 
  
Ports: ss -tulpn (or netstat -tulpn) — list one listening service and its port.
Nginx- 80
Name resolution: dig <domain> or nslookup <domain> — record the resolved IP.
ubuntu@ip-172-31-34-19:~$ dig www.google.com

; <<>> DiG 9.20.18-1ubuntu2.1-Ubuntu <<>> www.google.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 11988
;; flags: qr rd ra; QUERY: 1, ANSWER: 8, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 65494
;; QUESTION SECTION:
;www.google.com.                        IN      A

;; ANSWER SECTION:
www.google.com.         152     IN      A       142.251.153.119
www.google.com.         152     IN      A       142.251.157.119
www.google.com.         152     IN      A       142.251.152.119
www.google.com.         152     IN      A       142.251.151.119
www.google.com.         152     IN      A       142.251.150.119
www.google.com.         152     IN      A       142.251.154.119
www.google.com.         152     IN      A       142.251.155.119
www.google.com.         152     IN      A       142.251.156.119

;; Query time: 2 msec
;; SERVER: 127.0.0.53#53(127.0.0.53) (UDP)
;; WHEN: Mon Jun 01 18:40:08 UTC 2026
;; MSG SIZE  rcvd: 171

HTTP check: curl -I <http/https-url> — note the HTTP status code.
200
Connections snapshot: netstat -an | head — count ESTABLISHED vs LISTEN (rough).
netstat -an |head 
Active Internet connections (servers and established)
Proto Recv-Q Send-Q Local Address           Foreign Address         State      
tcp        0      0 0.0.0.0:22              0.0.0.0:*               LISTEN     
tcp        0      0 0.0.0.0:80              0.0.0.0:*               LISTEN     
tcp        0      0 127.0.0.54:53           0.0.0.0:*               LISTEN     
tcp        0      0 127.0.0.53:53           0.0.0.0:*               LISTEN     
tcp        0      0 172.31.34.19:22         3.16.146.5:18222        ESTABLISHED
tcp6       0      0 :::22                   :::*                    LISTEN     
tcp6       0      0 :::80                   :::*                    LISTEN     
udp        0      0 172.31.34.19:68         0.0.0.0:*    

---------------------
Which command gives you the fastest signal when something is broken?
dig
What layer (OSI/TCP-IP) would you inspect next if DNS fails? If HTTP 500 shows up?
TTP 500
Application
Server processed request but failed internally

Two follow-up checks you’d run in a real incident.
dig traceroute



