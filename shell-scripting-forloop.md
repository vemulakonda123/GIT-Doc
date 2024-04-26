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

## 3) checking  docker status is runking or not
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
