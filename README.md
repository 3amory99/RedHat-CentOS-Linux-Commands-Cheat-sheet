# RedHat-CentOS-Linux-Commands-Cheat-sheet
Explore the power of Linux (CentOS) commands for efficient data engineering. This repository provides a comprehensive collection of essential Linux commands tailored for data engineers. From file manipulation to data transformation and pipeline management. **It's mainly as a reference for me as a Data Engineer.**

# Overview
**Significantly and objectively in Data Engineering**
Welcome to the CentOS Red Hat Linux Command Cheat Sheet repository! Your ultimate quick reference guide for mastering essential commands, tips, and tricks to efficiently manage CentOS and Red Hat systems specifically for Data Engineering. Elevate your command-line skills and streamline administration with our comprehensive cheat sheet. Let's simplify CentOS and Red Hat Linux together! 

# Let's dive into RedHat-CentOS Linux Commands
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

## Basics Commands

```bash
# Go to '/var/www/'
mkdir directoryname                                          
```
```bash
# Create a directory
mkdir directoryname                                          
```
```bash
# Create a directory
mkdir directoryname                                          
```
```bash
# Create a directory
mkdir directoryname                                          
```
```bash
# Create a directory
mkdir directoryname                                          
```
```bash
# Create a directory
mkdir directoryname                                          
```
```bash
# Create a directory
mkdir directoryname                                          
```
```bash
# Create a directory
mkdir directoryname                                          
```
```bash
# Create a directory
mkdir directoryname                                          
```
--------------------------------------------------------------------------------------------------

</p>
</details>  


 <details><summary>Permission </summary>
<p>

```bash
#set suid bit such as -rwSr-xr-x. capital S means (rws)
chmod 4655 <file> 

```
```bash
#Setgid on dir, all dir/files in it will get same ownership as parent dir. It doesn't matter who is creating
```
```bash
#setting setgid bit
chmod g+s <dir/file> 
```
```bash
#setting sticky bit such as drwxrwxrwt. small t means (rwxt)
chmod 1777 <dir> 
```
```bash
#setting sticky bit such as drwxrwxrwT. capital T means (rwt)
chmod 1776 <dir> 
```
```bash
#asssigning recursive permission of all files/dir in  target dir
chown -R <user>:<group> <dir> 
```
</p>
</details>
  
  
<details><summary>User Administration</summary>
<p>

```bash
useradd -g itadmin -c "DB User" -u 1135 -s "/bin/sh" -d /home/techguy1 
#In the above command, we are creating the new user with custom options as simple "#useradd <user>" will create with default setting. The -g (group) -c (description) -u (user id) -s (which shell to be assigned) -d (landed home dir)
```
```bash
useradd -g <primary group> -G <secondary group> <user> # assign the user primary and secondary group

```
```bash
passwd -l <user> #locking password of user

```
```bash
passwd -u <user> #unlocking password of user

```
```bash
passwd -e <user> #expire password 

```
```bash
echo 'myPassword123' | sudo passwd --stdin <user> 

```
```bash
passwd -x -1 <user> #Turnoff password expiry

```
```bash
usermod -L <user> #locking user

```
```bash
usermod -U <user> #unlocking user

```
```bash
chage #set password expiry

```

</p>
</details>
 

<details><summary>Access Control Lists (ACLs)</summary>
<p>

```bash
setfacl -m u:priya:rw <file> #assiging the a new user 'priya' with read/write permission on the file. -m (modifying) -u (user)
```
```bash
setfacl -m mask:r <file> #setting mask on file
```
```bash
setfacl -d -m u:priya:rw <dir> #setting ACL for directory
```
```bash
getfacl -R <dir> > permissions.acl #BackUp ACL's in file having all info related ownership/dir inside the dir,subdir,files
```
```bash
setfacl --restore=permissions.acl #Restore the Permissions/Ownership
```

</p>
</details>


<details><summary>Crontab</summary>
<p>

```bash
crontab -l #show crontab for all users
```
```bash
crontab -u <user> -l #show crontab for specific user
```
```bash
crontab -e #add cron entry in crontab file
```

</p>
</details>


<details><summary>Process</summary>
<p>

```bash
ps -a #all terminal 
```
```bash
ps -e #list of all the processes
```
```bash
ps -o #customer properties

```
```bash
ps -ao tty,comm,pid,%mem,%cpu #<command/script> & #run the task in background

```
```bash
ps -fp $(pgrep -d, -x logrotate)

```
```bash
pgrep -u <userid> unison

```
```bash
ps -p <pid> -o etime #process execution time

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
hostnamectl set-hostname <hostname>

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


<details><summary>SFTP/SCP</summary>
<p>

```bash
sftp -oPort=<port> <user>@<ipaddress/domain>

```
```bash
sftp -oPort=<port> -oIdentityFile=<path to key> <user>@<ipaddress/domain>

```
```bash
sftp -o KexAlgorithms=<keyExchangeAlgo> -o HostKeyAlgorithms=<HostKeyAlgoName> -oIdentityFile=<path to key> -oPort=<port> <user>@<domain/ipaddress>

```
```bash
sftp -oPort=<port> -o KexAlgorithms=diffie-hellman-group14-sha1 -o HostKeyAlgorithms=+ssh-dss -oIdentityfile=<path to key> <user>@<domain/ipaddress>

```
```bash
scp -P <port> <path to src file> <user>@<domain/ipaddress>:<target path> #send the file to target system

```
```bash
scp -P <port> <user>@<domain/ipaddress>:<src file path> <target file path locally> #fetch/download file from the target system

```

```bash
scp -r /path/to/local/source user@ssh.example.com:/path/to/remote/destination #send dir from the target system

```

```bash
scp -r user@ssh.example.com:/path/to/remote/source /path/to/local/destination #fetch/download dirctory from the target system

```

</p>
</details>


<details><summary>Bolt</summary>
<p>

<i>For the --tmpdir flag we can use the home directory path of the remote user which will logged in on the behalf of the bolt. At some time /tmp is not executable due to which the command gets failed. (~mizz - will be confirm) </i>

```bash
bolt command run "<command>"  --no-host-key-check --tmpdir=/tmp -p <password>  --tty --targets @<ipaddress/hostname list file>  -u <user>

```
```bash
bolt command run "<command>"  --no-host-key-check --tmpdir=/tmp -p <password>  --tty --targets <ipaddress/hostname separate by ,>  -u <user>

```
```bash
bolt script run <script>  --no-host-key-check --tmpdir=/tmp -p <password>  --tty --targets @<ipaddress/hostname list file>  -u <user>

```
```bash
bolt script run <script>  --no-host-key-check --tmpdir=/tmp -p <password>  --tty --targets <ipaddress/hostname separate by ,>  -u <user>

```

</p>
</details>


<details><summary>Sed</summary>
<p>

```bash
sed -n -e "/<$hostname>/,/ismail.com/ p" <targetfile> #replace the string by variable, result will be stdout

```
```bash
sed -i -n -e "/<$hostname>/,/ismail.com/ p" <targetfile> #replace the string by variable, result will be saved in target file

```
```bash
sed -i 's/stringtoreplace/newstring/g' myfile.txt #replace the string from the file globally

```

</p>
</details>


<details><summary>find</summary>
<p>

```bash
find /tmp/* -mtime +7 -exec rm {} \; #remove files from dir "tmp/" that are older than 7 days 

```
```bash
find /home/ -type f -name ".errors*.gz" -mtime +7 -exec rm {} \; #remove files from dir "tmp/" that are older than 7 days - with filename

```
```bash
find /home/ -type f -size +500M -name "*tempfile*" -exec du -sh {} \; #found the tempfile that has file size >500MB

```
```bash
find /home/ -type f -size +1G -exec ls -lh {} \; | awk '{ print $9 "|| Size : " $5 }' #find output in custom defined format like in this "dirname || Size:_"

```

```bash
#Combine find exec multiple commands
find /tmp/dir1/ -type f -exec chown root:root {} \; -exec chmod o+x {} \;
``` 

```bash
#Combine find exec multiple commands
find /tmp/dir1/ -type f -exec chown root:root {} \; -exec chmod o+x {} \;
```
```bash 
#World-Writable dir
#CIS
find / -path /proc -prune -o -path /sys -prune -o -type d -perm -0002 -mindepth 3 -maxdepth 4 -printf "World-Writable dir %p\n" 2>/dev/null
```


```bash 
#find files with permission
find / -xdev \( -perm -4000 -o -perm -2000 \) -type f 
#4000 for suid, 2000 for guid
```
 
```bash
#Combine find exec shell script function
#[Ref: https://www.golinuxcloud.com/find-exec-multiple-commands-examples-unix/#:~:text=Linux%20or%20Unix.-,Find%20exec%20multiple%20commands%20syntax,%5C%3B%20or%20as%20%22%20%3B%20%22.]
find /tmp/dir1/ -type f -exec bash -c '
for item do
[[ $item =~ "file1" ]] && mv -v $item ${item}_renamed
done
' bash {} +
```

</p>
</details>


<details><summary>grep</summary>
<p>


```bash
cat myfile | grep -B 1 -A 4 -i 'string one\|string two' #it will show 1 line before and 4 lines after matching the strings form myfile

```
```bash
grep -lr "string" * #search recursively the string from all filesystem hierarchy, as its start from which current dir you are standing and it will list files

```
```bash
grep -ir "string" <* or file> #search recursively the string from all filesystem hierarchy and show the content what matches - * for all files otherwise specify a single file

```

```bash
grep -E -s "<regex>" <file>
#grep with -E extended regex -s with silent mode as no error message on screen
```

```bash
grep -P -s -- "<regex>" <file>
#grep with -P perl regex -s with silent mode as no error message on screen
```

```bash
grep -Eq '<regex>' <file> && grep -Eq '<regex>' file2 && result=pass
#grep with -E extended regex -q with quite mode as no error/stdout message on screen
```
 
</p>
</details>


<details><summary>Gzip/Tar/Compress directory</summary>
<p>

```bash
#The gzip command in Linux can only be used to compress a single file. In order to compress a folder, tar + gzip (which is basically tar -z) is used.
#ref: https://www.educative.io/edpresso/how-to-gzip-a-directory-in-linux
```

```bash
tar -zcvf myfolder.tar.gz myfolder #Compress folder/dir with -z in Linux

```
```bash
tar -tf myfolder.tar.gz #view the content of compressed file
```

```bash
gzip filename #view the content of compressed file
```

```bash
unzip file.gz #uncompress the zip file
```

</p>
</details>

<details><summary>AWK</summary>
<p>

```bash
#Multiple Conditional Statement - Not Equal, Regex, Equal
awk -F: '($1!="root" && $1!="sync" ) {print}' /etc/passwd
awk -F: '($1!="root" && $1!~/^\+/) {print}' /etc/passwd
awk -F: '($1=="virusgroup") {print $3}' /etc/group
du -sh * | grep G | awk '($1~/[0-9]+\.?[0-9]*G$/)'
awk '/^\s*UID_MIN/{print $2}' /etc/login.defs
df --local -P | awk {'if (NR!=1) print $6'} #skip first or header line
```
```bash
df --local -P | awk {'if (NR!=1) print $6'} #skip first or header line
```
```bash
#Variable in awk statement
awk -F: -v GID="$(awk -F: '($1=="shadow") {print $3}' /etc/group)" '($4==GID) {print $1}' /etc/passwd
```
```bash
#Awk result with loop
awk -F: -v GID="$(awk -F: '($1=="shadow") {print $3}' /etc/group)" '($4==GID) {print $1}' /etc/passwd | (while read -r usr; do
        [ -z "$output" ] && output="\"$usr\"" || output=",\"$usr\""
done
```

</p>
</details>
 
<details><summary>XARGS</summary>
<p>

```bash
#XARGS Application - to use last command result for next command
df --local -P | awk {'if (NR!=1) print $6'} | xargs -I '{}' find '{}' -xdev -nouser -printf "%p has no owner\n" 2>/dev/null

```
 
</p>
</details>
 
<details><summary>stat</summary>
<p>

```bash
stat -L -c "%A" "$dir"

```
```bash
stat --printf='Name: %n\nPermissions: %a\n' /etc

```
```bash
stat --printf='User: %U | Group: %G' /etc 

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

  
