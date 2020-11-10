# Linux commands

* [General](#General)
* [Packages](#Packages)
* [Users and Groups](#Users-and-Groups)
* [Search](#Search)
* [Environment variables](#Environment-variables)
* [File and directories](#File-and-directories)
* [Processes](#Processes)

## General

### Check the linux distribution

```txt
cat /proc/version
cat /etc/os-release
```

#### Check the hard disk size

```txt
df -h
```

### Download a file with wget

```txt
wget --user="<username>" --password="<username>" https://domain/attachments.tar.gz

Eventually verify the SHA-1 checksum

sha1sum attachments.tar.gz
```

### GREP

```txt
https://alvinalexander.com/linux-unix/recursive-grep-r-searching-egrep-find

Arguments
-l This flag tells grep to print the matching filenames.
-r Recursive search
-i Ignore case, case insensitive

Serach for the string 'git' in all files in the current directory
grep -rl git .


- Search multiple subdirectories
grep -rl git ./.git ./shell/


- Using egrep recursively (using multiple pattern)
egrep -rl 'git|cat' ./shell/
```

## Packages

### Install packages from .deb file

```txt
sudo apt install ./<file_name>.deb
```

### List of all packages installed

```txt
sudo apt list --installed
sudo apt list --installed | less
```

### List all added repositores

```txt
grep ^ /etc/apt/sources.list /etc/apt/sources.list.d/*

cat /etc/apt/sources.list /etc/apt/sources.list.d/*

grep -r --include '*.list' '^deb ' /etc/apt/sources.list*
```

### Snap

```txt
https://tutorials.ubuntu.com/tutorial/basic-snap-usage#1

snap list
snapp install pkg_name
snapp remove pkg_name
```

### Remove repository

```txt
sudo rm /etc/apt/sources.list.d/skype-stable.list
sudo rm /etc/apt/sources.list.d/skype-stable.list.save
```

## Users and Groups

### Show Linux System groups

```txt
cat /etc/group
```

### Add a new group

```txt
sudo groupadd <group_name>
```

### Add user to group

```txt
sudo useradd -g <group_name> -d /home/db2instl -m <user_login>
```

### Create user password

```txt
sudo passwd <user_login>
```

## Search

### Search everywhere

```txt
sudo find / -name <file_name>
```

### Find into jar

```txt
find -name "*.jar" | xargs grep <ClassName>.class
```

## Environment variables

### Define a new variable

```txt
export WORKSPACE_HOME=/home/workspace
```

### Use a variable

```txt
touch $WORKSPACE_HOME/readme.md
```

## File and directories

### Rename a folder

```txt
mv /home/db2inst1 /home/db2instl
```

### Ubuntu file manager

```txt
Ctrl + H    Show / Hide hidden files
Ctrl + L    Edit address bar
```

## Processes

### Find process

```txt
https://man7.org/linux/man-pages/man1/ps.1.html

ps aux | grep -i firefox

ps -ef | grep 8888
```

### Find process running on port

```txt
lsof -i :9990
```

### Kill process running on port

```txt
sudo kill `sudo lsof -t -i:9990`
```

### See which process is using a file, a directory, a socket

```txt
fuser 8888/tcp
```
