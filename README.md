# HAZESOFT-T3
script for backup

I created the repo named as “HAZESOFT-T3” in github account.
Then i created the file “bacup.sh” inside the hazesoft/shellscript using following command
mkdir hazesoft
cd hazesoft
mkdir shellscript
touch backup.sh
Then i write the following command inside the backup.sh file
#!/bin/bash

# check if directory path is provided as an argument

if [ "$#" -ne 1 ]; then
echo "Usage:$0 ./shellscript"
exit 1
fi

# Input directory to backup

source_directory="$1"

# Backup directory
backup_directory="backup"
mkdir -p "$backup_directory"

#Timestamp for the backupd file
timestamp=$(date "+%Y%m%d_%H%M%S")
backup_filename="$backup_directory/$timestamp.tar.gz"

#Create compressed tar archive
tar czf "$backup_filename" "$source_directory"

#check id the backup was successful
if [ $? -eq 0 ]; then 
echo "backup successed ..archived saved as :$backup_filename"
else
echo "error :backup failed"
fi

Then i saved it.
Then i run the command for backuping the file.
bash backup.sh ../shellscript


Then backup is done..

