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
