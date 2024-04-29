## cpu load average value check
```
#!/bin/bash
echo "cpu load average value check"
load=`top -bn1 | grep load | awk '{printf "%.2f%%\t\t\n", $(NF-2)}'| cut -d '%' -f1`
echo $load
if [[ ${load%.*} > 1 ]];
then
        echo "cpu load is very high: $load"
else
        echo "load is normal"
fi
```
