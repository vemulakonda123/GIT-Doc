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
## 5) Added to crontab to check every minite ,when service is stoped it automatically starts
```
ubuntu@ip-10-0-0-55:~$ crontab -l
# For example, you can run a backup of all your user accounts
# at 5 a.m every week with:
# 0 5 * * 1 tar -zcf /var/backups/home.tgz /home/
#
# For more information see the manual pages of crontab(5) and cron(8)
#
# m h  dom mon dow   command
* * * * * /home/ubuntu/httpd-status.sh
```
## Installing multiple softwares 
## Very simple and easy
```
 1 #!/bin/bash
  2 #Author: hhv
  3 #Installing multiple packages
  4
  5 if [ $# -eq 0 ]
  6 then
  7         echo "Usage:please provide software names as command line arguments"
  8         echo "$#"
  9         exit 1
 10 fi
 11
 12 if [[ $(id -u) -ne 0 ]]
 13 then
 14         echo "please run from root user or with sudo privilage"
 15         exit 2
 16 fi
 17
 18
 19 for software in $@
 20 do
 21         if which $software &> /dev/null
 22         then
 23            echo "Already $software is installed"
 24         else
 25           echo "installing $software...."
 26           apt-get install $software -y &> /dev/null
 27           if [[ $? -eq 0 ]]
 28           then
 29                   echo "successfully installed $software package"
 30           else
 31                   echo "unable to install $software"
 32         fi
 33         fi
 34 done
 ```

### Read command in shell with flages
```
root@ip-10-0-0-55:/home/ubuntu# read -a fruits
apple jjk ppp

root@ip-10-0-0-55:/home/ubuntu# echo $fruits
apple
root@ip-10-0-0-55:/home/ubuntu# echo "${fruits[0]}, ${fruits[1]}, ${fruits[2]}"
apple, jjk, ppp
```
```
root@ip-10-0-0-55:/home/ubuntu# read -s -p "Enter your password: " password
Enter your password: 
root@ip-10-0-0-55:/home/ubuntu# echo $password
mypassword-was -hidden
#Here -s will hidd
```
```
read -n 4 -p "Enter a 4-character code: " code
echo "Code entered: $code"
#here -n 4 represent that it will take only 4 char or number 
```

![image](https://github.com/vemulakonda123/GIT-Doc/assets/50296141/d3e51508-dc90-47c1-b400-89679547b987)
```
### "read <options> <arguments>"
```
### writting content into test.txt file
```
#!/bin/bash
echo "while loop demo..."
while read -r line;
do
        echo "$line"
done > test.txt
```

## status check
## give inputs like docker, apache2...
## which will tell weather they are running or not
```
#!/bin/bash
echo "service status check script"
read -p "Enter service name to check:" service_name
if [ -z $service_name ];
then
        echo "please provide any service name "
else
        systemctl status $service_name
fi
```

## grep command 
![image](https://github.com/vemulakonda123/GIT-Doc/assets/50296141/99a9033f-3073-4cd5-84cb-f9e5c56c79ae)
```
root@ip-10-0-0-55:~# vi grep-command.txt
=================
root@ip-10-0-0-55:~# grep devops grep-command.txt
When you the devops is boom
devops is the courece
the moo to devops
=================
root@ip-10-0-0-55:~# grep -i devops grep-command.txt
Devops is good
we will filter DEVOPS
When you the devops is boom
you are low to Devops
devops is the courece
the moo to devops
DEVOPS is boom
root@ip-10-0-0-55:~# grep -c devops grep-command.txt
3
===========
root@ip-10-0-0-55:~# grep -ic devops grep-command.txt
7
==============
root@ip-10-0-0-55:~# grep -o devops grep-command.txt
devops
devops
devops
==============
root@ip-10-0-0-55:~# grep -w devops grep-command.txt
When you the devops is boom
devops is the courece
the moo to devops
==================
root@ip-10-0-0-55:~# grep -n devops grep-command.txt
4:When you the devops is boom
6:devops is the courece
7:the moo to devops
================
root@ip-10-0-0-55:~# grep -in devops grep-command.txt
1:Devops is good
3:we will filter DEVOPS
4:When you the devops is boom
5:you are low to Devops
6:devops is the courece
7:the moo to devops
8:DEVOPS is boom
====================
root@ip-10-0-0-55:~# grep -v devops grep-command.txt
Devops is good
by using grep command
we will filter DEVOPS
you are low to Devops
DEVOPS is boom
========================
root@ip-10-0-0-55:~# grep -iv devops grep-command.txt
by using grep command
root@ip-10-0-0-55:~#
```

## ERROR CHECK in log file
```
matched_error=`grep -i error /var/log/messages`
echo $matched_error
if [[ $? -eq 0 ]];
then
	echo "found error in os logs: $matched_error "
else
	echo "no error in message logs"
fi
```

