# LINUX-COMMANDS

Certainly! Here’s the list of commands formatted in code boxes:

```sh
# System Monitoring and Performance --------------------------------

# Real-time system processes and resource usage
top

# Interactive process viewer (requires installation)
htop

# System memory, processes, and CPU statistics
vmstat

# CPU and I/O statistics
iostat

# Displays memory usage
free -h

# Collects, reports, or saves system activity information (requires `sysstat` package)
sar -u 1 3

# Disk Usage and Management -----------------------------------

# Reports disk space usage
df -h

# Displays disk usage of files and directories
du -sh /path/to/directory

# Lists block devices
lsblk

# Partition table manipulator for Linux
sudo fdisk -l

# A more advanced partitioning tool
sudo parted /dev/sdX

# Network Configuration and Troubleshooting ----------------------------------

# Configures network interfaces (deprecated, replaced by `ip`)
ifconfig

# Shows/manages IP addresses, routes, and interfaces
ip addr show

# Tests network connectivity
ping example.com

# Traces the route packets take to a network host
traceroute example.com

# Displays network connections, routing tables, and interface statistics
netstat -tuln

# Utility to investigate sockets (more modern than `netstat`)
ss -tuln

# Queries DNS to obtain domain name or IP address mapping
nslookup example.com

# Performs DNS lookups
dig example.com

# System Services and Processes ----------------------------------------

# Manages system services and the system state
systemctl status service-name

# Manages services (deprecated in favor of `systemctl`)
service service-name status

# Displays information about active processes
ps aux

# Shows real-time system processes and resource usage
top

# File System and Disk Operations ------------------------------------------------

# Mounts file systems
mount /dev/sdXn /mnt/mountpoint

# Unmounts file systems
umount /mnt/mountpoint

# Changes file modes or Access Control Lists
chmod 755 filename

# Changes file owner and group
chown user:group filename

# Searches for files in a directory hierarchy
find /path -name filename

# Searches for patterns within files
grep 'pattern' file

# User and Group Management -----------------------------------

# Adds a new user
sudo useradd username

# Modifies a user account
sudo usermod -aG groupname username

# Changes user password
sudo passwd username

# Adds a new group
sudo groupadd groupname

# Security and Logs ---------------------------------------------------

# Uncomplicated Firewall, used to manage firewall rules
sudo ufw status

# Configures network packet filtering rules
sudo iptables -L

# Queries and displays logs from `systemd` journal
journalctl -xe

# Prints kernel ring buffer messages
dmesg | less

# Backup and Recovery ------------------------------------------------

# Synchronizes files and directories between two locations
rsync -av source/ destination/

# Archives files into tarballs
tar -czvf archive.tar.gz /path/to/directory

# Converts and copies files (useful for disk cloning)
dd if=/dev/sdX of=/path/to/backup.img bs=4M

# System Information -------------------------------------------

# Displays system information
uname -a

# Displays CPU architecture information
lscpu

# Lists block devices
lsblk

# Lists hardware information (requires installation)
sudo lshw
```

Feel free to copy and use these commands as needed for system administration tasks.

<hr>

Here's a well-organized Linux commands cheat sheet categorized into relevant sections:

### SYSTEM
- **Display System Information**
  - `uname -a` : Display Linux system information
  - `uname -r` : Display kernel release information
  - `uptime` : Show how long the system has been running
  - `hostname` : Show system hostname
  - `last reboot` : Show system reboot history
  - `date` : Show the current date and time
  - `cal` : Show this month's calendar
  - `w` : Display who is online
  - `whoami` : Show who you are logged in as

### FILE PERMISSIONS
- **Change Permissions**
  - `chmod octal file-name` : Change the permissions of a file to octal (e.g., `chmod 777 /data/test.c`)
  - `chmod 755 /data/test.c` : Set `rwx` permission for owner, `rw` for group and world
- **Change Ownership**
  - `chown owner-user file` : Change the owner of the file
  - `chown owner-user:owner-group file-name` : Change owner and group of the file
  - `chown owner-user:owner-group directory` : Change owner and group of the directory

### NETWORK
- **Network Configuration**
  - `ifconfig -a` : Display all network ports and IP addresses
  - `ifconfig eth0` : Display specific Ethernet port
  - `ethtool eth0` : Show Ethernet status
  - `mii-tool eth0` : Show Ethernet status
- **Network Diagnostics**
  - `ping host` : Send echo request to test connection
  - `whois domain` : Get whois information for domain
  - `dig domain` : Get DNS information for domain
  - `dig -x host` : Reverse lookup host
  - `netstat -tupl` : List active connections to/from the system
  - `wget file` : Download file

### HARDWARE
- **Hardware Information**
  - `dmesg` : Detected hardware and boot messages
  - `cat /proc/cpuinfo` : CPU model
  - `cat /proc/meminfo` : Hardware memory
  - `lshw` : Display hardware configuration
  - `lsblk` : Block device related information
  - `lsusb` : Show USB devices
  - `dmidecode` : Show hardware info from the BIOS
  - `hdparm -i /dev/sda` : Show info about disk `sda`
  - `hdparm -t /dev/sda` : Do a read speed test on disk `sda`
  - `badblocks -s /dev/sda` : Test for unreadable blocks on disk `sda`

### USERS
- **User Management**
  - `id` : Show the active user ID with login and group
  - `last` : Show last logins on the system
  - `who` : Show who is logged on the system
  - `useradd "Sam Tomshi"` : Create user `Sam Tomshi`
  - `userdel sam` : Delete user `sam`
  - `usermod` : Modify user information

### FILE COMMANDS
- **File Operations**
  - `ls -al` : Display all information about files/directories
  - `pwd` : Show the path of the current directory
  - `mkdir directory-name` : Create a directory
  - `rm file-name` : Delete file
  - `rm -rf directory-name` : Forcefully remove directory recursively
  - `cp file1 file2` : Copy file1 to file2
  - `cp -r dir1 dir2` : Copy directory dir1 to dir2, create dir2 if it doesn't exist
  - `mv file1 file2` : Rename/move file1 to file2
  - `touch file` : Create or update a file
  - `cat file` : Output contents of file
  - `more file` : Output contents of file, paging
  - `head file` : Output first 10 lines of file
  - `tail file` : Output last 10 lines of file
  - `tail -f file` : Output contents of file as it grows

### COMPRESSION/ARCHIVES
- **Archive Operations**
  - `tar -cf home.tar /home` : Create a tar archive named `home.tar` containing `/home/`
  - `tar -xf file.tar` : Extract the files from `file.tar`
  - `tar -czf file.tar.gz files` : Create a tar with gzip compression
  - `gzip file` : Compress file and rename it to `file.gz`

### INSTALL PACKAGE
- **Package Management**
  - `rpm -i pkgname.rpm` : Install rpm-based package
  - `rpm -e pkgname` : Remove package

### INSTALL FROM SOURCE
- **Build from Source**
  - `./configure` : Prepare the build system
  - `make` : Compile the source code
  - `make install` : Install the compiled program

### SEARCH
- **Search Commands**
  - `grep pattern files` : Search for pattern in files
  - `grep -r pattern dir` : Search recursively for pattern in directory
  - `locate file` : Find all instances of file
  - `find /home/tom -name "index"` : Find files named "index"
  - `find /home -size +10000k` : Find files larger than 10000k in `/home`

### FILE TRANSFER
- **Transfer Files**
  - `scp file.txt user@host:/tmp` : Securely copy `file.txt` to remote host `/tmp` folder
  - `rsync -a /home/apps/backup/ user@host:/backup/` : Synchronize source to destination

### DISK USAGE
- **Disk Usage**
  - `df -h` : Show free space on mounted filesystems
  - `du -ah` : Show disk usage in human-readable form
  - `du -sh` : Display total disk usage on the current directory
  - `fdisk -l` : Show disk partitions sizes and types

### PROCESS RELATED
- **Process Management**
  - `ps` : Display your currently active processes
  - `ps aux | grep telnet` : Find all process IDs related to telnet
  - `pmap` : Memory map of process
  - `top` : Display all running processes
  - `kill pid` : Kill process with mentioned PID
  - `killall process-name` : Kill all processes named `process-name`
  - `pkill process-name` : Send signal to a process with its name

### DIRECTORY TRAVERSE
- **Directory Navigation**
  - `cd ..` : Go up one level of the directory tree
  - `cd ~` : Go to home directory
  - `cd /test` : Change to `/test` directory

### LOGIN (SSH AND TELNET)
- **Remote Login**
  - `ssh user@host` : Connect to host as user
  - `ssh -p port user@host` : Connect to host using specific port
  - `telnet host` : Connect to the system using telnet

### OTHER USEFUL COMMANDS
- **Miscellaneous**
  - `od` : Octal dump
  - `xargs` : Execute command lines from standard input
  - `wc` : Print the number of bytes, words, and lines in files
 
<hr>


