# Linux Commands Cheat Sheet

### System Info Commands

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


```
User Management Commands
ac — Total connect time for all users or specified users.
The ac command reads the /var/log/wtmp file, which contains binary data about every login, logout, system event, and current status on the system. It gets its data from the wtmp file.
Display total login time of a specific user.
ac john
Display total login time for each user.
ac -p
Display total login time for each day.
ac -d
Display total login time for the current day.
ac -d -p
Display login time from a specific log file.
ac -f /var/log/wtmp
useradd - Creates a user account.
useradd <userName> - Creates user account without home & mail spool directories.
Example: useradd bot
useradd -m <userName> - Creates user account with home & mail spool directories.
Example: useradd -m bot
passwd <userName> - The system generates a password for the user and then stores it in the /etc/shadow file.
userdel - Deletes User Account.
userdel <userName> - deletes the user from the system.
userdel -r <userName> - deletes the user from the system along with home and mail spool directories.
Example: userdel -r bot
/etc/passwd - Stores information about user accounts.
cat /etc/passwd - displays the complete list of users on that machine.
/etc/shadow - stores the password for users in an encrypted format.
cat /etc/shadow - displays the complete list of user passwords on that machine.
su - substitute user.
su <userName> - switches to the user mentioned.
exit - to logout from that user.
Example: su - ram
usermod - modify user.
usermod -aG <groupName> <userName> - adds the user to another group (-aG append the user to the group without removing from other groups).
Example: usermod -aG mygroup ram
chsh - change shell.
chsh -s /bin/bash <user> - changes the shell to bash for the user.
chsh -s /bin/sh <user> - changes the shell to sh for the user.
Example: chsh -s /bin/sh ubuntu
Group Management Commands
groupadd <groupName> - creates the group.
groupdel <groupName> - delete the group.
/etc/group - stores the information of the groups.
cat /etc/group - displays the complete list of groups on that machine.
gpasswd <groupName> - creates a password for the group.
gpasswd -a <userName> <groupName> - adds the user to the group.
gpasswd -d <userName> <groupName> - removes the user from the group.
gpasswd -M <userName1>,<userName2>,<userName3> <groupName> - adds multiple users to the group and removes the existing ones of the group.
Searching Commands
find — Search for files/directories based on their names.
find . -name <fileName> - finds the mentioned file if available in the current directory (.(period) represents current directory).
find <dirName> -name <fileName> - finds the mentioned file in the directory.
find <dirName> -perm 754 - finds the files in the directory having 754 permission.
locate is faster for finding files by name due to its pre-built database, while find is more versatile, allowing complex searches based on various criteria in real-time.
locate - Search for files/directories based on their names.
locate <fileName/dirName> - locates the file/directory and displays the path.
Example: locate crazy.txt
GREP Command — Global Regular Expression Print
grep <textToSearch> <fileName> - used to find text patterns within files.
grep -i <textToSearch> <fileName> - used to find text patterns within the file ignoring the case (-i ignore case).
grep -v <textToSearch> <fileName> - used to find non matching lines of text patterns (-v invert-match).
grep -l <textToSearch> <fileNames> - used to display the matching string file names.
Example: grep -l welcome crazy.txt
There are additional commands related to grep.
egrep (or grep -E)
fgrep (or grep -F)
zgrep (for compressed files)
zegrep (or zgrep -E for compressed files)
bzgrep (for compressed files)
ack-grep (Ack)
Hardware Infomation Commands
free -h - Display system memory information in human-readable format (-h).
df -h - It displays the disk space usage of mounted file systems.
du - Disk usage.
du -h - Display disk usage information in human-readable format.
du -sh - Display the total size of the directory in human-readable format, summarizing the size instead of listing individual file sizes.
du -sh <fileName/dirName> - Displays the total size of the file/directory.
Connection To Remote System
ssh - Secure Shell: Connect to a remote server securely.
Example: ssh user@remote_host
scp - Securely Copy Files: Copy files between local and remote systems using SSH.
Example: scp file.txt user@remote_host:/path
rsync - Remote Sync: Synchronize files and directories between systems.
Example: rsync -avz local_folder/ user@remote_host:remote_folder/
Network Commands
nc — Simple tcp proxy, network daemon testing
Example: nc -vz google.com 443
ping <hostName> - tests the reachability & responsiveness of the remote host.
Example: ping google.com -c 2 (-c pings 2 times)
dig <domainName> - Shows DNS information of the domain.
Example: dig medium.com
wget <url>- Used to retrieve/download files from the internet.
curl - client URL.
curl <url> - Used to retrieve/download files from the internet.
ifconfig - Display available network interfaces.
ip addr - Display and manipulate network interface info.
curl ifconfig.me - Shows the public ip address of the machine.
netstat -antp- shows all tcp open ports (-a all, t-tcp, n-active, p protocol).
traceroute <url> - traces the route using packets from source to destination host.
Process Information Commands
ps - Process status.
ps - Displays the currently running process.
ps -u <userName>- Displays the process of the username
ps -ef - Displays all the processes of the system.
top - Shows the real-time, dynamic view of the running processes of a system.
kill <pid> - Gracefully terminates the process pid(-9 forcefull).
pgrep <processName> - Shows process id of processes based on name/other criteria.
bg - background, sends the process to the background & continues execution without interruption.
fg - foreground, brings the process to the foreground and makes it an active process.
nohup - no hangup, runs command/script in the background even after the terminal is closed or the user logs out.
Example: nohup ./script.sh
<command> & — Using in last of command runs in background, allowing you to continue using the terminal while the command runs asynchronously.
Example: ./script.sh &
Archiving File Commands
tar - tape archive.
tar -cvf <fileName> <directory> - creates the tar file with the fileName for the directory mentioned (-c create, -v verbose, -f output file name).
tar -xvf <sourceTarFileName> -C <destinationDir> - puts the extracted files into the destination directory (-x extract, -v verbose, -f source tar file name, -C change the folder and download to destination dir).
Ubuntu Package related Commands
apt - Package Manager for Debian-based Linux distributions Eg: Ubuntu.
apt - Anewer version of the package manager with colorized output, progress bar and additional functions.
apt-get - Older version and basic package manager.
apt update - Updates the package list.
apt list --installed - Lists all the installed packages.
apt list --installed <packageName> - shows the package name if it's installed.
apt show <packageName> - shows information about a package mentioned.
apt search <packageName> - searches and shows the list of packages.
apt install <packageName> - installs the required package.
apt remove <packageName> - removes the required package.
apt purge <packageName> - removes the required package along with its config files.
Note: For other package manager just replace “apt” with other package manager
Directory Commands
pwd - shows the present working directory (abbr. Print Working Directory).
cd - change directory.
cd .. - changes to its parent directory (i.e) one level up.
cd <dirName> - change to the directory mentioned.
cd ~ or cd - changes to the currently logged in user's home directory.
cd ../.. - changes the directory two levels up.
cd - - changes to the last working directory.
mkdir - make directory.
mkdir <dirName> - creates the directory.
mkdir -p <pathOftheDir> - creates directory with its parent directories if it does not exists (-p parent).
ls - lists the files & folders of the directory you are in.
ls -a - lists all files & folders along with hidden files (-a all).
ls -al - lists all files & folders along with hidden files in a formatted manner (-l long listing format).
Misc Commands
man - Displays the manual page for a specific command. Provides detailed information and usage instructions.
sed - Edits a stream of text by substituting occurrences of a pattern with another.
awk - A powerful programming language for text processing.
wc -(Word Count)
ln -(Create Links):
stat <fileName/dirName> - shows detailed information about the file or directory.
cron - system daemon for managing scheduled tasks.
crontab -Used to create, edit, and manage cron jobs.
tree - Representation of files and directories of a specific directory.
echo "sample text" | grep text - The output of the first command is passed as an input to the second command using the pipe (|) symbol.
ls -l | tee file.txt - Redirects the list to the file.txt and simultaneously displays it in the terminal.
echo "sample text" > <fileName> - Write the content to the file mentioned by overwriting the existing content (> redirection operator).
echo "new sample text" >> <fileName> - Appends the contents to the file mentioned without overwriting the existing content (>> redirection operation).
```
