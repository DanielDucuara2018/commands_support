# Linux Overview

## General Commands

```sh
man man
cd <FOLDER_NAME> # move to a given folder
cd .. # back to the parent folder
cd /  # back to root folder

ls # list of element in a folder
ls -a # list all files (even hidden folders and files)
ls -l # mode list of element in a folder
pwd #Current folder 

touch <FILE_NAME> # create a new file
rm <FILE_NAME> # remove a file
mkdir <FOLDER_NAME> # create a folder
rmdir <FOLDER_NAME> # remove a folder
mv <FILE_LOCATION> <DESTINATION> # move file to a given destination
chmod -R 777 <FOLDER_NAME>
cat <FILE_NAME> # show file content

top # show running processes
env # show enviroment variables
ps aux | grep <NAME_PROCESS_FILTER>
kill -9 <PID>

export <ENV_VARIABLE> = <LOCATION>


sudo alien <PACKAGE_FILE>.rpm
sudo dpkg -i <PACKAGE_FILE>.deb

# CTRL + R for searching an already used linux command 
# Ctrl+Alt+Maj+R for recording my computer windows

which <NAME_APP> #find app location
```
