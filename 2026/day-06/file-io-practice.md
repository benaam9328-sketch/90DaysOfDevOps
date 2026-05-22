------Day06-----------------------------------
[root@ip-172-31-28-123 ~]# touch notes.txt
[root@ip-172-31-28-123 ~]# echo"Hello my name in Kachaan Nice to meet you!" > notes.txt
-bash: echoHello my name in Kachaan Nice to meet you!: command not found
[root@ip-172-31-28-123 ~]# echo "Hello my name in Kachaan Nice to meet you!" > notes.txt
[root@ip-172-31-28-123 ~]# echo "Hello my name in Kachaan Nice to meet you!" >> notes.txt
[root@ip-172-31-28-123 ~]# echo "Hello my name in Kachaan Nice to meet you!" > notes.txt
[root@ip-172-31-28-123 ~]# cat notes.txt
Hello my name in Kachaan Nice to meet you!
[root@ip-172-31-28-123 ~]# echo "Hello my name in Kachaan Nice to meet you!1" > notes.txt
echo "Hello my name in Kachaan Nice to meet yousudo -i" > notes.txt
[root@ip-172-31-28-123 ~]# cat notes.txt
Hello my name in Kachaan Nice to meet yous 2
[root@ip-172-31-28-123 ~]# echo "Hello my name in Kachaan Nice to meet you!" > notes.txt //overwrites
[root@ip-172-31-28-123 ~]# echo "Hello my name in Kachaan Nice to meet you2" >> notes.txt
[root@ip-172-31-28-123 ~]# echo "Hello my name in Kachaan Nice to meet you3" >> notes.txt //appends
[root@ip-172-31-28-123 ~]# echo "Hello my name in Kachaan Nice to meet you4" >> notes.txt
[root@ip-172-31-28-123 ~]# head -n2 notes.txt
Hello my name in Kachaan Nice to meet you!
Hello my name in Kachaan Nice to meet you2
[root@ip-172-31-28-123 ~]# tail -n2 notes.txt
Hello my name in Kachaan Nice to meet you3
Hello my name in Kachaan Nice to meet you4
[root@ip-172-31-28-123 ~]# touch notes2.txt
[root@ip-172-31-28-123 ~]# echo "My name is Midoriya" | tee notes2.txt
My name is Midoriya
[root@ip-172-31-28-123 ~]# echo "My name is Midoriya2" | tee notes2.txt //overwrites existing content of file
My name is Midoriya2
[root@ip-172-31-28-123 ~]# cat notes2.txt
My name is Midoriya2
[root@ip-172-31-28-123 ~]# echo "My name is Midoriya3" | tee -a notes2.txt //append
My name is Midoriya3
[root@ip-172-31-28-123 ~]# cat notes2.txt
My name is Midoriya2
My name is Midoriya3
