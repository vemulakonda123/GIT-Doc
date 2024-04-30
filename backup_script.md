## Here iam taking backup of directorys and copying to destination
## Wonderfull and easy to understand
```
#!/bin/bash

backup_dirs=("/home/ubuntu/text_dir" "/home/ubuntu/shell_script-dir")
dest_dir="/home/ubuntu/backup_dir"
mkdir -p $dest_dir
backup_date=$(date +%b-%d-%y)
echo "staring backup of: ${backup_dirs[@]}"
for i in "${backup_dirs[@]}"; do
sudo tar -Pczf $i-$backup_date.tar.gz $i
if [ $? -eq 0 ]; then
echo "$i backup successed..."
else
echo "$i backup failed.."
fi
cp $i-$backup_date.tar.gz $dest_dir
if [ $? -eq 0 ]; then
echo "$i transfer successed..."
else
echo "$i transfer failed.."
fi
done
sudo rm /home/ubuntu/*.gz
echo "Backup is done..."
```
