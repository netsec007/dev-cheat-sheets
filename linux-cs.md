# Linux Commands Cheat Sheet

###System Info Comaands

hostname - Show system hostname

```
hostname
```

hostid - Show system ID assigned by the OS

```
hostid
```

date - Show current date and time in UTC formt

```
date
```

uptime - Show uptime since last boot

```
uptime
```

uname - Show unix name

```
uname
```

clear - clear the screen

```
clear
```

history - show all commands executed until now

```
history
```

sudo - Super User Do

```
sudo su - USERNAME
```

shutdown -r now - restart machine now

```
shutdown -r now
```

printenv - show all environment variables of the system

```
printenv
```

last - show previous login to the system

```
last
```

systemctl - System Control (manage services using systemd)

```
systemctl status sshd
systemctl stop sshd
systemctl start sshd
systemctl restart sshd
```

### File Commands

touch - create empty file or update timestamp of existing file
 
```
touch <filename>
touch <file1> <file2>
```

cat or bat - concatenates and displays content of a file

```
cat <filename>
cat > <filename> - creates a new file, allows to input content redirects inputted content to the created file
```

head - displays first 10 lines(default) of a file

```
head <filename>
head -n 5 <filename> - displays 5 lines
```

tail - displays last 10 lines(default) of a file

```
tail <filename>
tail -n 5 <filename> - displays 5 lines
tail -F <filename> - displays last lines in real-time
```

less - displays large files in a paginated manner

```
less <filename>
```

rm - remove command

```
rm <filename>
rm -r <dirName> removes files and folders of directory(recursive)
rm -rf <dirName> force remove - use cautously
```

cp - copy command

```
cp <source> <destination>
cp -r <dir1> <dir2> - copy dir1 directory to dir2 directory(recursively)
```

### File Permission Commands

ls - list files

```
ls
ls -l
ls -ld
```
chmod - change file/directory permission

File permission octals

read (r) — 4, write (w)- 2, execute (x) — 1 * Sum the numbers to generate an octal number for setting permissions on a file or directory
```
chmod <octalNumber> <fileName> - changes mode/permissions of the file
chmod <octalNumber> -R <dirName> - changes mode/permissions of the directory recursively
chown <newUser> <fileName> - changes the user ownership of a file
```

chown - change file/directory ownership

```
chown <newUser> <fileName>
```

chgrp - change file/directory group membership

```
chgrp <groupName> <fileName/dirName>
```

getfacl - shows the file/directory access control list

```
getfacl <fileName/dirName>
```

setfacl - modifies the current acl of the file/directory

```
setfacl -m u:<userName>:rwx <fileName/dirName> - modifies the current acl of the file/directory
setfacl -x u:<userName>: <fileName/dirName> - removes the acl permissions for the file/directory
setfacl -m g:<groupName>:rwx <fileName/dirName> - modifies the group acls for the file/directory
setfacl -x g:<groupName>: <fileName/dirName> - removes the group acl permissions for the file/directory
```
