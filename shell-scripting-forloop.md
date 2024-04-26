## For loop 
### 1) This script takes multiple filenames as input and prints their contents.
```
#!/bin/bash
# This script takes multiple filenames as input and prints their contents.

for filename in "$@"; do
  echo "The contents of the file $filename are:"
  cat "$filename"
done
```
### 2) searching for directorys in the form of for-loop and find perticular test folder and delete... 
```
#!/bin/bash
echo "searching for directorys and deleting them "
for folder in $(find  -type d); do
        echo "the folder is $folder"
if [ -d test ]; then
        echo "this folder is exist"
        rm -rf test
        echo "successfully deleted"
else
        echo "directory not found"
fi
done
```

## 3) checking  docker status is running or not
```
#!/bin/bash
echo "status check of docker service"
status="`systemctl status docker | awk 'NR==3 {print }' | cut -d ':' -f 2 | cut -d '(' -f 1`"
echo $status
if [ $status = '"active" ];
then
	echo "service is running fine................."
else
	echo "service is not running"
fi
```
## 4) important example for cut and awk commands

```
ubuntu@ip-10-0-0-55:~$ systemctl status apache2
● apache2.service - The Apache HTTP Server
     Loaded: loaded (/lib/systemd/system/apache2.service; enabled; vendor preset: ena>
     Active: active (running) since Fri 2024-04-26 16:50:29 UTC; 1h 22min ago
       Docs: https://httpd.apache.org/docs/2.4/
   Main PID: 17810 (apache2)
      Tasks: 55 (limit: 1121)
     Memory: 5.1M
        CPU: 276ms
     CGroup: /system.slice/apache2.service
             ├─17810 /usr/sbin/apache2 -k start
             ├─17812 /usr/sbin/apache2 -k start
             └─17813 /usr/sbin/apache2 -k start

Apr 26 16:50:29 ip-10-0-0-55 systemd[1]: Starting The Apache HTTP Server...
Apr 26 16:50:29 ip-10-0-0-55 apachectl[17809]: AH00558: apache2: Could not reliably d>
Apr 26 16:50:29 ip-10-0-0-55 systemd[1]: Started The Apache HTTP Server.
lines 1-16/16 (END)

ubuntu@ip-10-0-0-55:~$ systemctl status apache2 | awk 'NR==3 {print}'
     Active: active (running) since Fri 2024-04-26 16:50:29 UTC; 1h 23min ago
ubuntu@ip-10-0-0-55:~$ systemctl status apache2 | awk 'NR==3 {print}'|cut -d ':' -f 2
 active (running) since Fri 2024-04-26 16
ubuntu@ip-10-0-0-55:~$ systemctl status apache2 | awk 'NR==3 {print}'|cut -d ':' -f 2|cut -d '(' -f 1
 active
ubuntu@ip-10-0-0-55:~$
```

