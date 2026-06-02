--------------
doneee
---------------------
cat access.log | tee /home/ubuntu/nginx-logs.txt
scp -i "Test-key.pem" ubuntu@3.4.3.19:/~ nginx-logs.txt .
copy nginx-logs.txt file from ec2 located in /home/ubuntu/ and dest . (where you are currently running the command)
----

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/91410b6a-34a8-49a4-975e-b8dc80007ab8" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/6c8d6d04-f676-42db-9f88-43f07c452724" />

