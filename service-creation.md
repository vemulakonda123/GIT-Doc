![image](https://github.com/vemulakonda123/GIT-Doc/assets/50296141/1c8718eb-7e8f-4b9c-b00c-b0186b8c44f3)

![image](https://github.com/vemulakonda123/GIT-Doc/assets/50296141/49e1e9f6-7ac2-4968-8b9d-34fbba3bd4e6)

![image](https://github.com/vemulakonda123/GIT-Doc/assets/50296141/f4ff8ef9-383a-45d9-a33e-d62cffcd15d1)


## Here iam creating a shell-scripting to monitor disk every 120sec and send log to specified path..,,but to run that shell-script we create service 
### 1) shell-script to monitor and send logs continious per every 120 sec
```
#!/bin/bash

#checking disk utlization for every 120 sec
# Here iam using while loop without providing any variable ,,,,that means we want to run loop continuously..
while true
do
        sudo date >> /var/log/fs-monitor
        sudo df -h >> /var/log/fs-monitor
        sleep 120
done
```
### 2) service creation under /lib/systemd/system/fs-monitor.service
```
root@ip-10-0-0-55:/home/ubuntu# cat /lib/systemd/system/fs-monitor.service
[Unit]
Description=FS monitoring service
Documentation=https://github.com/vemulakonda123/GIT-Doc

[Service]
Type=simple
User=root
Group=root
TimeoutStartSec=0
Restart=on-failure
RestartSec=30s
#ExecStartPre=
ExecStart=/home/ubuntu/disk-utliz-for-120sec.sh      ### shell-script path is here...to run continously
SyslogIdentifier=Diskutilization
#ExecStop=

[Install]
WantedBy=multi-user.target
```
## Checking output by  systemctl status fs-monitor.service
```
root@ip-10-0-0-55:/home/ubuntu# systemctl start fs-monitor.service
root@ip-10-0-0-55:/home/ubuntu# systemctl status fs-monitor.service
● fs-monitor.service - FS monitoring service
     Loaded: loaded (/lib/systemd/system/fs-monitor.service; disabled; vendor p>
     Active: active (running) since Tue 2024-04-30 19:15:54 UTC; 9s ago
       Docs: https://github.com/vemulakonda123/GIT-Doc
   Main PID: 4578 (disk-utliz-for-)
      Tasks: 2 (limit: 1121)
     Memory: 680.0K
        CPU: 20ms
     CGroup: /system.slice/fs-monitor.service
             ├─4578 /bin/bash /home/ubuntu/disk-utliz-for-120sec.sh
             └─4583 sleep 120

Apr 30 19:15:54 ip-10-0-0-55 systemd[1]: Started FS monitoring service.
Apr 30 19:15:54 ip-10-0-0-55 sudo[4579]:     root : PWD=/ ; USER=root ; COMMAND>
Apr 30 19:15:54 ip-10-0-0-55 sudo[4579]: pam_unix(sudo:session): session opened>
Apr 30 19:15:54 ip-10-0-0-55 sudo[4579]: pam_unix(sudo:session): session closed>
Apr 30 19:15:54 ip-10-0-0-55 sudo[4581]:     root : PWD=/ ; USER=root ; COMMAND>
Apr 30 19:15:54 ip-10-0-0-55 sudo[4581]: pam_unix(sudo:session): session opened>
Apr 30 19:15:54 ip-10-0-0-55 sudo[4581]: pam_unix(sudo:session): session closed>
lines 1-19/19 (END)
root@ip-10-0-0-55:/home/ubuntu#
```

