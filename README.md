# RedHat-CentOS-Linux-Commands-Cheat-sheet
Explore the power of Linux (CentOS) commands for efficient data engineering. This repository provides a comprehensive collection of essential Linux commands tailored for data engineers. From file manipulation to data transformation and pipeline management. **It's mainly as a reference for me as a Data Engineer.**

# Overview
**Significantly and objectively in Data Engineering**
Welcome to the CentOS Red Hat Linux Command Cheat Sheet repository! Your ultimate quick reference guide for mastering essential commands, tips, and tricks to efficiently manage CentOS and Red Hat systems specifically for Data Engineering. Elevate your command-line skills and streamline administration with our comprehensive cheat sheet. Let's simplify CentOS and Red Hat Linux together! 

# Let's dive into RedHat-CentOS Linux Commands
<details><summary>Linux file System Hierarchy</summary>
<img src="https://1.bp.blogspot.com/-UQ7-sWd_J4w/WmhKIFx7_fI/AAAAAAAAHIE/tixi5SsyI5YzoJygq_JQKL50axe2cAcrQCLcBGAs/s1600/Untitled.png">
</details>
<details><summary>System Information</summary>

<p>

```bash   
#Show computer architecture 
arch
```
```bash
#Show kernel version
uname -r
```
```bash
#Show system date
date 
```
```bash
#Show calendar table for 2023
date 2023
```
</p>
</details>
  
<details><summary>Files and Directories Commands</summary>
<p>

### Basic Commands with files and directories

```bash
# Go to '/var/www/'
cd /var/www/                                          
```
```bash
# Go to the upper level directory
cd ..                                         
```
```bash
# Go to home directory
cd                                           
```
```bash
# Another way to go to home directory
cd ~                                       
```
```bash
# Go to home directory of “user”
cd ~user                                         
```
```bash
# Go to the last directory
cd -                                         
```
```bash
# Print current directory path
pwd                                         
```
```bash
# Show the contents of the current directory
ls                                          
```
```bash
# Show the contents of the current directory adding characters to the names characterizing the type
ls -F                                          
```
```bash
# Show detailed representation of files and directories in the current directory
ls -l                                          
```
```bash
# Show hidden files and directories in the current directory
ls -a                                          
```
```bash
# List directories including hidden
ls -a|--all                                                  
```
```bash
# Show directories by modification time, newest first
ls -t                                         
```
```bash
# List all files recursively in a directory
ls -lR                                          
```
```bash
 # Lists all files recursively in a directory, including hidden files, and saves the output to standard output
ls -laR                                         
```
```bash
# Create a directory called ‘test’ in the current path
mkdir test                                         
```
```bash
# Create two directories simultaneously
mkdir dir1 dir2                                         
```
```bash
# Create a directory tree
mkdir -p /var/www/test/dir
```
--------------------------------------------------------------------------------------------------

</p>
</details>  
<details><summary>File Commands</summary>
<p>

### Creating, Rmoving, Moving, files
--------------------------------------------------------------------------------------------------
```bash
# Create file or update existing files 
touch file.txt
```
```bash
# Create or update more than one file
touch file1.txt file2.txt file3.txt
```
```bash
# Create multiple files
touch {file1,file2,file3}.txt
```
```bash
# Create file1, file2 and file3 multiple files
touch file{1..3} 
```
```bash
# Copy files, Copy file1 in file2
cp file1 file2
```
```bash
# Delete the file named file
rm -f file
```
```bash
# Delete a directory named ‘dir’ and all of its contents recursively
rm -rf dir
```
```bash
# Rename or move a file or directory
mv file.txt /path/file.txt
```
```bash
# Rename or move a file or directory
mv file.txt newfile.txt
```
### Linking files
--------------------------------------------------------------------------------------------------
We have in CentOS Linux two types of Linking first type is hard link second type is soft (sympolic) link
```bash
# Hard Link
ln file1 /path/file2
```
```bash
# Sympolic Link
ln -s /path/file1 /path/file2
```
```bash
# Show where symbolic links are pointing
ln -l
```
### Reading and Writing Files
--------------------------------------------------------------------------------------------------
```bash
# Determine file type
file
```
```bash
# Print all contents
cat file.txt
```
```bash
# Print some contents
less file.txt
```
```bash
# View the contents of a file one page
more file.txt
```
```bash
#  Print the default : top 10 lines of file
head file.txt
```
```bash
#  Print the default : bottom 10 lines of file
tail file.txt
```
```bash
#  Open the file in vim editor
vim file.txt
```
```bash
#  Open the file in nano editor
nano file.txt
```
```bash
#  Count inside file, list number of lines words and characters in the file
wc file.txt
```
```bash
#  Count the lines in the file
wc -l file.txt
```
```bash
#  Count the characters in the file
wc -c file.txt
```
```bash
#  Overwrite file with content
echo "New Line" > file.txt
```
```bash
#  Append to file with content
echo "New Line">> file.txt
```
--------------------------------------------------------------------------------------------------

</p>
</details>

<details><summary>Directory Commands</summary>
<p>

### Creating, Rmoving, Moving, Directories
--------------------------------------------------------------------------------------------------
```bash
# Create Directory 
mkdir dir
```
```bash
# Create multiple Directories
mkdir dir1 dir2 dir3 dir4
```
```bash
# Create nested directory
mkdir -p|--parents dir1/dir2
```
```bash
# Create a temporary directory
mktemp -d|--dir
```
```bash
# Delete empty directory
rmdir dir
```
```bash
# Delete directory including contents
rm -r dir
```
```bash
# move a directory
mv dir /path/dir
```
```bash
# Rename a directory
mv dir1 newdir
```
```bash
# Rename and move a directory
mv dir1 /path/newdir
```
```bash
# Rename or move a file or directory
mv file.txt newfile.txt
```
--------------------------------------------------------------------------------------------------
</p>
</details>
<details><summary>Searching</summary><p>

### Finding Files

#### locate
Uses an index and is fast.

```bash
# Update the index
updatedb
```
```bash
# Find a file using locate command
locate file
```
```bash
# Find a text file starting with 'f'
locate f*
```

#### find 
It doesn't use an index and is slow.

```bash
# Find a file
find /path -name file
```
```bash
# Find a file with another way
find /path -type f -name file
```
```bash
# Find a file with case insensitive search
find /path -iname file
```
```bash
# Find all text files
find /path -name "*.txt"
```
```bash
# Find a file and delete it
find /path -name file -delete
```
```bash
# Find a directory
find /path -type d -name dir
```
```bash
# Find a symbolic link
find /path -type l -name file
```
```bash
# Find files that haven't been modified in 30 days
find /path -type f -mtime +30
```
--------------------------------------------------------------------------------------------------

#### Find inside Files
*grep*

```bash
# Search for 'foo' in file 'file.txt'
find /path -type f -mtime +30grep 'foo' /file.txt
```
```bash
# Search for 'foo' in directory
grep 'foo' /directory -r|--recursive 
```
--------------------------------------------------------------------------------------------------
</p>
</details>
 <details><summary>Permissions</summary>
<p>

  
chmod u[+-=](rwx)or(
chown ahmed:data data
## File Permissions

| # | Permission              | rwx | Binary |
| - | -                       | -   | -      |
| 7 | read, write and execute | rwx | 111    |
| 6 | read and write          | rw- | 110    |
| 5 | read and execute        | r-x | 101    |
| 4 | read only               | r-- | 100    |
| 3 | write and execute       | -wx | 011    |
| 2 | write only              | -w- | 010    |
| 1 | execute only            | --x | 001    |
| 0 | none                    | --- | 000    |

For a directory, execute means you can enter a directory.

| User | Group | Others | Description                                                                                          |
| -    | -     | -      | -                                                                                                    |
| 6    | 4     | 4      | User can read and write, everyone else can read (Default file permissions)                           |
| 7    | 5     | 5      | User can read, write and execute, everyone else can read and execute (Default directory permissions) |

- u - User
- g - Group
- o - Others
- a - All of the above


```bash
# List file permissions
ls -l 
```
```bash
# Give the user execute permission
chmod u+x file.sh 
```
```bash
# Give the group execute permission
chmod g+x file 
```
```bash
# Take away the user and group execute permission
chmod u-x,g-x file
```
```bash
# Give everybody reading permission
chmod u+r,g+r,o+r file
```
```bash
# Give everybody reading permission by another way
chmod 777 file 
```
```bash
# Set suid bit such as -rwSr-xr-x. capital S means (rws)
chmod 4655 <file> 
```
```bash
# Setting setgid bit
chmod g+s <dir/file> 
```
```bash
# Setting sticky bit such as drwxrwxrwt. small t means (rwxt)
chmod 1777 <dir> 
```
```bash
# Setting sticky bit such as drwxrwxrwT. capital T means (rwt)
chmod 1776 <dir> 
```
```bash
# Asssigning recursive permission of all files/dir in  target dir
chown -R <user>:<group> <dir> 
```
```bash
# Change the owner
chown USER file 
```
</p>
</details>
  
  
<details><summary>User Administration</summary>
<p>

### User and Group Management

### User Management
```bash
# In this command, we are creating the new user with custom options as simple "#useradd <user>" will create with default setting. The -g (group) -c (description) -u (user id) -s (which shell to be assigned) -d (landed home dir)
useradd -g itiadmin -c "DB User" -u 1135 -s "/bin/sh" -d /home/techguy1 
```
```bash
# assign the user primary and secondary group
useradd -g <primary group> -G <secondary group> <user> 
```
```bash
# assign the user primary and secondary group
useradd -g <primary group> -G <secondary group> <user> 
```
```bash
# assign the user primary and secondary group
useradd -g <primary group> -G <secondary group> <user> 
```
```bash
# Add the user "user" to the group "group".
usermod -aG groub user
```
```bash
# Add the user "username" to the "wheel" group, which typically grants administrative privileges.
usermod -aG wheel user
```
```bash
# Locking user
usermod -L user
```
```bash
# Unlocking user
usermod -U user
```
```bash
# Delete user
userdel user
```
```bash
# Command-line tool for deleting a user and also deletes his home directory.
userdel -r user
```
```bash
# Displays information about the user with the specified username.
id user
```
```bash
# Displays all the users exists in the os.
cat /etc/passwd
```
--------------------------------------------------------------------------------------------------
### Group Management


```bash
 # Command-line tool for creating a new group.
 groupadd groupname
```
```bash
# removes an existing group
groupdel groupname
```
```bash
# Lists the groups that the current user belongs to.
 groups 	
```
```bash
# Displays information about the group 
id group
```
```bash
# Displays the system's group database
cat /etc/group
```
--------------------------------------------------------------------------------------------------
### Password Management

```bash
#locking password of user
passwd -l <user> 
```
```bash
#unlocking password of user
passwd -u <user> 
```
```bash
#expire password 
passwd -e <user> 
```
```bash
echo 'myPassword123' | sudo passwd --stdin <user> 
```
```bash
#Turnoff password expiry
passwd -x -1 <user> 
```
```bash
#locking user
usermod -L <user> 
```
```bash
#unlocking user
usermod -U <user> 
```
```bash
#set password expiry
chage 
```
```bash
# Changes the password aging settings for the user "user03".
chage -m 0 -M 90 -W 7 -I 14 user03 
```
</p>
</details>
<details><summary>Access Control Lists (ACLs)</summary>
<p>
  
```bash
# Displays the ACLs for the specified file.
getfacl <file> 
```
```bash
# Assiging the a new user 'omar' with read/write permission on the file. -m (modifying) -u (user)
setfacl -m u:omar:rw <file> 
```
```bash
# Setting mask on file
setfacl -m mask:r <file> 
```
```bash
# Setting ACL for directory
setfacl -d -m u:omar:rw <dir> 
```
```bash
# BackUp ACL's in file having all info related ownership/dir inside the dir,subdir,files
getfacl -R <dir> > permissions.acl
```
```bash
# Restore the Permissions/Ownership
setfacl --restore=permissions.acl 
```
</p>
</details>
<details><summary>Process</summary>
<p>

```bash
# List all processes interactively
top  
```
```bash
# List all processes interactively
htop  
```
```bash
# All terminal
ps 
```
```bash
# All process
ps aux | grep 
```
```bash
# All terminal
ps -a  
```
```bash
# List of all the processes
ps -e 
```
```bash
# Customer properties
ps -o 
```
```bash
# <command/script> & #run the task in background
ps -ao tty,comm,pid,%mem,%cpu 
```
```bash
ps -fp $(pgrep -d, -x logrotate)
```
```bash
pgrep -u <userid> unison
```
```bash
# Process execution time
ps -p <pid> -o etime 
```
```bash
ps -eo user,pid,ppid,%mem,%cpu --sort=-%cpu | head
```
```bash
ps lax
```
```bash
ps fax
```
```bash
# Sleep for 30 seconds and move the process into the background
sleep 30 &
```
```bash
# List all background jobs
jobs
```
```bash
# Resume a suspended process and run in the background
bg
```
```bash
# Bring the last background process to the foreground
fg
```
```bash
# Change process priority by name
nice -n -20 PName
```
```bash
# Change process priority by PID
renice 20 PID
```
```bash
# Return the process priority of PID
ps -o ni PID
```
```bash
# Kill a process running in the foreground
CTRL+C
```
```bash
# Shut down process by PID gracefully. Sends TERM signal
kill PID 
```
```bash
# Shut down process by name gracefully. Sends TERM signal
pkill PName 
```
```bash
# Kill all process with the specified name gracefully
killall PName 
```
</p>
</details>


<details><summary>SystemD and Services</summary>
<p>

```bash
# Controls the systemd system and service manager
systemctl  
```
```bash
# Displays help information about systemd unit types
systemctl -t help  
```
```bash
# Lists all active systemd services on the system
systemctl list-units -t service 
```
```bash
# Starts a systemd service with the specified name
systemctl start ___
```
```bash
# Stops a systemd service with the specified name
systemctl stop  
```
```bash
# Restarts a systemd service with the specified name
systemctl restart 
```
```bash
# Reloads the configuration of a systemd service with the specified name
systemctl reload 
```
```bash
# Enables a systemd service with the specified name to start automatically at boot time
systemctl enable
```
```bash
# Disable a systemd service with the specified name to start automatically at boot time
systemctl disable
```
```bash
# Checks if a systemd service with the specified name is currently active
systemctl is-active ___
```
```bash
# Reloads the configuration of a systemd service with the specified name, or restarts it if the reload fails
systemctl reload-or-restart ___  
```
```bash
# Displays the status of the "sshd" systemd service.
systemctl status sshd.service
```
</p>
</details>

<details><summary>Network</summary>
<p>

```bash
dig +trace www.google.com
```
```bash
nmcli dev status
```
```bash
nmcli con del <interface name>
```
```bash
ip addr show <interface name>
```
```bash
nmcli con show
```
```bash
nmcli con add con-name <interface name> type <ethernet> ifname <interface name> ip4 <ip address> gw4 <gateway>
```
```bash
nmcli con up <interface name>
```
```bash
nmcli con mod <interface name> ipv4.gateway <ip address>
```
```bash
# Displays or sets the system's hostname
hostname 
```
```bash
hostnamectl set-hostname <hostname>
```
```bash
# Displays the current hostname and related information
hostnamectl status
```
```bash
netstat -rn

```
```bash
route -n

```
```bash
tcpdump -i <interface>

```
```bash
tcpdump -i <interface> host <ipaddress>  -nn

```
```bash
tcpdump -i <interface> -s 0 -w <output file name example.pcap> host <ipaddress/hostname> and udp

```
```bash
ping <hostname/ipaddress>

```
```bash
telnet <hostname/ipaddress> <port>

```
```bash
nslookup <domain/hostname>

```
```bash
netstat -an |grep <ipaddress>.<port>|grep ESTAB|awk '{print $5}'|awk -F: '{print $1}'|sort|uniq -c|sort -rn #show which remote hosts make how many connection to specfic port, the output is sort on number of connections by host to port 

```

</p>
</details>


<details><summary>SSH Service</summary>
<p>

#### Secure Shell Protocol (SSH)

```bash
# Connect to hostname using your current user name over the default SSH port 22
ssh hostname 
```
```bash
# Connect to hostname using the identity file
ssh -i identityfile.pem hostname
```
```bash
# Connect to hostname using the user over the default SSH port 22
ssh user@hostname 
```
```bash
# Connect to hostname using the user over a custom port
ssh user@hostname -p 8765
```
```bash
# Create a private key and matching public key
ssh-keygen -t rsa
```
```bash
# Determines the files where the keys are saved
ssh-keygen -f .ssh/key-with-pass
```
```bash
# Copies the public key of the SSH key pair to the destination system
ssh-copy-id -i .ssh/key-with-pass.pub user@hostname
```
```bash
# Authenticate to the host system using the corresponding private key
ssh -i .ssh/key-with-pass user@hostname 
```

```bash
# Set default user and port in ~/.ssh/config, so you can just enter the name next time
$ cat ~/.ssh/config
Host name
  User foo
  Hostname 127.0.0.1
  Port 8765
$ ssh name
```
</p>
</details>



<details><summary>Memory</summary>
<p>


```bash
egrep --color 'Mem|Cache|Swap' /proc/meminfo | awk '{print $1 " " $2/1000/1000 "GB"}' #show information in GB

```
```bash
smem -s swap -t -k -n -r

```
```bash
smem -u -p -r

```
```bash
free -h

```

</p>
</details>


<details><summary>Disk</summary>
<p>

```bash
df -h

```
```bash
df -Th

```
```bash
du -sh <path/*>

```
```bash
df --local -P #in KBs
```
```bash
du -sch .[!.]* * | grep --regex="[0-9]*G"

```
```bash
lsof -u <user> #list of openfiles by specific user

```
```bash
lsof | grep delete #list of openfiles that are deleted

```
```bash
lsof | awk '{print $1}' | sort | uniq -c | sort -r -n #sort number of open files by process

```

</p>
</details>

<details><summary>grep</summary>
<p>

```bash
# It will show 1 line before and 4 lines after matching the strings form myfile
cat myfile | grep -B 1 -A 4 -i 'string one\|string two' 
```
```bash
# Search recursively the string from all filesystem hierarchy, as its start from which current dir you are standing and it will list files
grep -lr "string" * 
```
```bash
# Search recursively the string from all filesystem hierarchy and show the content what matches - * for all files otherwise specify a single file
grep -ir "string" <* or file> 
```
```bash
# grep with -E extended regex -s with silent mode as no error message on screen
grep -E -s "<regex>" <file>

```
```bash
# grep with -P perl regex -s with silent mode as no error message on screen
grep -P -s -- "<regex>" <file>
```
```bash
# grep with -E extended regex -q with quite mode as no error/stdout message on screen
grep -Eq '<regex>' <file> && grep -Eq '<regex>' file2 && result=pass
```
</p>
</details>


<details><summary>Gzip/Tar/Compress directory</summary>
<p>

```bash
#The gzip command in Linux can only be used to compress a single file. In order to compress a folder, tar + gzip (which is basically tar -z) is used.
#ref: https://www.educative.io/edpresso/how-to-gzip-a-directory-in-linux
```
--------------------------------------------------------------------------------------------------

#### tar

```bash
# Creates a tar archive named "archive.tar" containing the specified files.
tar cvf archive.tar file1 file2 file3 
```
```bash
# Lists the contents of a tar archive without extracting it
tar tf archive.tar 
```
```bash
# Compress folder/dir with -z in Linux
tar -zcvf myfolder.tar.gz myfolder
```
```bash
# View the content of compressed file without extracting it
tar tf myfolder.tar.gz 
```

```bash
# View the content of compressed file
gzip filename 
```
```bash
unzip file.gz #uncompress the zip file
```
</p>
</details>
<details><summary>lsof</summary>
<p>
```bash
lsof -u <user> #list the openfiles by a user
```
</p>
</details>
<details><summary>Bash Scripting</summary>
<p>
  
## Bash Profile

--------------------------------------------------------------------------------------------------

- bash - `.bashrc`
- zsh - `.zshrc`

```bash
# Always run ls after cd
function cd {
  builtin cd "$@" && ls
}

# Prompt user before overwriting any files
alias cp='cp --interactive'
alias mv='mv --interactive'
alias rm='rm --interactive'

# Always show disk usage in a human readable format
alias df='df -h'
alias du='du -h'
```

## Bash Script

--------------------------------------------------------------------------------------------------

### Variables

--------------------------------------------------------------------------------------------------

```bash
#!/bin/bash

foo=123                   # Initialize variable v_name with 123
declare -i v_name=123     # Initialize an integer foo with 123
declare -r v_name=123     # Initialize readonly variable v_name with 123
echo $v_name              # Print variable v_name
echo ${v_name}_'bar'      # Print variable v_name followed by _bar
echo ${v_name:-'default'} # Print variable v_name if it exists otherwise print default

export v_name             # Make v_name available to child processes
unset v_name              # Make v_name unavailable to child processes
```

### Environment Variables

--------------------------------------------------------------------------------------------------

```bash
#!/bin/bash

env               # List all environment variables
echo $PATH        # Print PATH environment variable
export v_name=123 # Set an environment variable
```

### Functions

--------------------------------------------------------------------------------------------------

```bash
#!/bin/bash

greet() {
  local world = "World"
  echo "$1 $world"
  return "$1 $world"
}
greet "Hello"
greeting=$(greet "Hello")
```

--------------------------------------------------------------------------------------------------

### Exit Codes

```bash
#!/bin/bash

exit 0   # Exit the script successfully
exit 1   # Exit the script unsuccessfully
echo $?  # Print the last exit code
```

### Conditional Statements

--------------------------------------------------------------------------------------------------

#### Boolean Operators

- `$v_name` - Is true
- `!$v_name` - Is false

#### Numeric Operators

- `-eq` - Equals
- `-ne` - Not equals
- `-gt` - Greater than
- `-ge` - Greater than or equal to
- `-lt` - Less than
- `-le` - Less than or equal to
- `-e` foo.txt - Check file exists
- `-z` foo - Check if variable exists

#### String Operators

- `=` - Equals
- `==` - Equals
- `-z` - Is null
- `-n` - Is not null
- `<` - Is less than in ASCII alphabetical order
- `>` - Is greater than in ASCII alphabetical order

#### If Statements

--------------------------------------------------------------------------------------------------

```bash
#!/bin/bash

if [[$v_name = 'bar']]; then
  echo 'one'
elif [[$v_name = 'bar']] || [[$v_name = 'baz']]; then
  echo 'two'
elif [[$v_name = 'ban']] && [[$USER = 'bat']]; then
  echo 'three'
else
  echo 'four'
fi
```

#### Inline If Statements

--------------------------------------------------------------------------------------------------

```bash
#!/bin/bash

[[ $USER = 'rehan' ]] && echo 'yes' || echo 'no'
```
--------------------------------------------------------------------------------------------------

#### While Loops

```bash
#!/bin/bash

declare -i counter
counter=10
while [$counter -gt 2]; do
  echo The counter is $counter
  counter=counter-1
done
```
--------------------------------------------------------------------------------------------------

#### For Loops

```bash
#!/bin/bash

for i in {0..10..2}
  do
    echo "Index: $i"
  done

for filename in file1 file2 file3
  do
    echo "Content: " >> $filename
  done

for filename in *;
  do
    echo "Content: " >> $filename
  done
```
--------------------------------------------------------------------------------------------------

#### Case Statements

```bash
#!/bin/bash

echo "What's the weather like tomorrow?"
read weather

case $weather in
  sunny | warm ) echo "Nice weather: " $weather
  ;;
  cloudy | cool ) echo "Not bad weather: " $weather
  ;;
  rainy | cold ) echo "Terrible weather: " $weather
  ;;
  * ) echo "Don't understand"
  ;;
esac
```
--------------------------------------------------------------------------------------------------
</p>
</details>  
<details><summary>Other</summary>
<p>

```bash
top -b -n 1 | head -n +5
```
```bash
uptime
```
```bash
sestatus #check selinux status
```
```bash
collectl -sc -p /var/log/collectl/server1-20220411-000000.raw.gz --top --from 00:00-03:00 -oTm
collectl -scn -p /var/log/collectl/server2-20220411-000000.raw.gz --from 00:15-00:41 --top
collectl -scD -p server1-000000.raw.gz --from 00:00-00:55 --top iokb | grep -w 'cp\|sdb\|Wait\|Pct\|PID' | less
```
</p>
</details>
