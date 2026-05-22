------Used httpd serice for the drill---------
For each test I have created the simulation then worked on troubleshooting

CPU usage 100% simulation with heavy I/O.
  Steps-
        a) sudo yum install httpd-tools -y
        b)created heavy php-page
                         <?php
              while(true) {
                  sha1(rand());
              }
              ?>
        c) ab -n 100000 -c 200 http://localhost/stress.php
        Troubleshoot
        1)Top
        2)ps -aux | grep hhtpd
        3) vmstat -1
        4)tail -f /var/log/httpd/access_log
        5)tail -f /var/log/httpd/error_log
        4)free -h
        4) restarted httpd service(when things worsen )
        6)pkil ab

        
