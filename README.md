
```sh
Check which program is running this port
sudo lsof -i :9043
sudo netstat -tulnp | grep 9043
sudo ss -tulnp | grep 9043
sudo fuser 9043/tcp

sudo ufw allow 9090/tcp - allows firewall traffic on port 9090:
cmd - netstat and ss and
cmd - sudo ethtool enp0s3
./prometheus --web.listen-address=":9043" &

sudo ufw status
sudo ufw enable
sudo ufw allow 9043/tcp
sudo ufw allow 9043/udp
sudo ufw deny 9043/tcp

```
<hr>

# LINUX-COMMANDS

> ## Comprehensive list of Linux commands that System Administrators, Network Administrators, Security Analysts, DevOps Engineers, and Technical Support Engineers might use daily. These commands cover a wide range of tasks including network management, system monitoring, and troubleshooting.

### General System Commands

- **System Information**
  - `uname -a` : Displays system information.
  - `hostname` : Shows the system's hostname.
  - `uptime` : Shows how long the system has been running.
  - `top` : Displays real-time system processes and resource usage.
  - `htop` : An enhanced version of `top` with a more user-friendly interface.
  - `dmesg` : Displays kernel-related messages.
  - `free -h` : Shows memory usage.

- **File System Commands**
  - `df -h` : Shows disk space usage of file systems.
  - `du -sh` : Displays disk usage of files and directories.
  - `ls -l` : Lists files and directories with detailed information.
  - `find /path -name filename` : Searches for files and directories.
  - `stat filename` : Displays file or file system status.

- **Process Management**
  - `ps aux` : Shows a snapshot of current processes.
  - `kill <pid>` : Terminates a process by PID.
  - `pkill processname` : Terminates processes by name.
  - `killall processname` : Kills all processes with the given name.

- **Service Management**
  - `systemctl status service` : Checks the status of a service.
  - `systemctl start service` : Starts a service.
  - `systemctl stop service` : Stops a service.
  - `systemctl restart service` : Restarts a service.
  - `systemctl enable service` : Enables a service to start on boot.
  - `systemctl disable service` : Disables a service from starting on boot.

### Network Commands

- **Network Monitoring**
  - `netstat -tuln` : Displays all listening ports and their associated IP addresses.
  - `ss -tuln` : Provides similar information to `netstat`, often faster and more informative.
  - `ip a` : Shows detailed information about network interfaces.
  - `ping host` : Checks the reachability of a host.
  - `traceroute host` : Displays the route packets take to a network host.
  - `mtr host` : Combines `ping` and `traceroute` for more detailed network diagnostics.
  - `nmap -sP subnet` : Scans a subnet for active devices.

- **Network Configuration**
  - `ifconfig` : Configures network interfaces (older tool, replaced by `ip`).
  - `ip link set dev interface up` : Brings an interface up.
  - `ip link set dev interface down` : Brings an interface down.
  - `iwconfig` : Configures wireless network interfaces.

- **Network Traffic Analysis**
  - `tcpdump` : Captures network traffic.
  - `wireshark` : GUI-based network traffic analyzer.
  - `iftop` : Displays bandwidth usage on an interface.
  - `bmon` : Bandwidth monitor and rate estimator.

### Security Commands

- **User and Group Management**
  - `useradd username` : Adds a new user.
  - `usermod -aG groupname username` : Adds a user to a group.
  - `passwd username` : Changes a user's password.
  - `groupadd groupname` : Creates a new group.
  - `groupdel groupname` : Deletes a group.
  - `deluser username` : Deletes a user.

- **File Permissions and Ownership**
  - `chmod 755 file` : Changes file permissions.
  - `chown user:group file` : Changes file ownership.

- **Security Tools**
  - `fail2ban-client status` : Checks the status of fail2ban.
  - `ufw status` : Checks the status of the Uncomplicated Firewall.
  - `iptables -L` : Lists current firewall rules.

### DevOps and Automation Commands

- **Docker**
  - `docker ps` : Lists running containers.
  - `docker exec -it container /bin/bash` : Opens a shell inside a running container.
  - `docker-compose up` : Starts services defined in `docker-compose.yml`.

- **Kubernetes**
  - `kubectl get pods` : Lists Kubernetes pods.
  - `kubectl describe pod podname` : Shows details about a specific pod.
  - `kubectl apply -f file.yaml` : Applies configuration changes from a YAML file.

- **Configuration Management**
  - `ansible-playbook playbook.yml` : Runs an Ansible playbook.

- **Version Control**
  - `git status` : Shows the status of a Git repository.
  - `git pull` : Pulls changes from a remote repository.
  - `git push` : Pushes changes to a remote repository.

### System Diagnostics and Maintenance

- **Logs and Monitoring**
  - `tail -f /var/log/syslog` : Displays the end of a log file and updates in real-time.
  - `journalctl -xe` : Shows system logs.
  - `logwatch` : Summarizes system logs.

- **Backup and Restore**
  - `rsync -av source destination` : Synchronizes files and directories.
  - `tar -czvf archive.tar.gz /path` : Creates a compressed archive of files.

### Miscellaneous Commands

- **System Updates**
  - `apt update` : Updates the package index.
  - `apt upgrade` : Upgrades installed packages.
  - `yum update` : Updates packages on RHEL/CentOS.

- **Package Management**
  - `dpkg -l` : Lists installed packages.
  - `rpm -qa` : Lists all installed RPM packages.

These commands are fundamental for the daily tasks of IT professionals across various roles and are essential for effective system and network management.

<hr>

> Important Linux cmds for cloud Engineer check internet & Network port connection info:

- netstaat --help - `use this to know what you have requred to check`
- netstat - `Troubleshoot Network Issues`
   - netstat -putan | grep :8080 - `check what is running on this port`
   - netstat more
   - netstat -at | more - `for TCP connection`
   - netstat -au | more - `for UDP connection`
   - netstat -atlnp | more - `check also what programm is runnig on port`
   - netstat -r - `routing table information`
```sh
 -r, --route              display routing table
        -i, --interfaces         display interface table
        -g, --groups             display multicast group memberships
        -s, --statistics         display networking statistics (like SNMP)
        -M, --masquerade         display masqueraded connections

        -v, --verbose            be verbose
        -W, --wide               don't truncate IP addresses
        -n, --numeric            don't resolve names
        --numeric-hosts          don't resolve host names
        --numeric-ports          don't resolve port names
        --numeric-users          don't resolve user names
        -N, --symbolic           resolve hardware names
        -e, --extend             display other/more information
        -p, --programs           display PID/Program name for sockets
        -o, --timers             display timers
        -c, --continuous         continuous listing

        -l, --listening          display listening server sockets
        -a, --all                display all sockets (default: connected)
        -F, --fib                display Forwarding Information Base (default)
        -C, --cache              display routing cache instead of FIB
        -Z, --context            display SELinux security context for sockets
```
## vmstat - `Virtual Memory Statistics`

`vmstat` command ka use system performance ko monitor karne ke liye kiya jata hai. Iska full form hai "Virtual Memory Statistics." Yeh command aapko system ke various resources ki statistics provide karta hai, jaise ki memory, swap, I/O, system activity, etc. Ye information system administrators aur performance analysts ke liye bahut useful hoti hai.

### Output Explanation

- **Procs**: Process-related information. `r` (running processes) aur `b` (blocked processes).
- **Memory**: Memory usage. `swpd` (swap space), `free` (free memory), `buff` (buffer memory), `cache` (cache memory).
- **Swap**: Swap space statistics. `si` (swap in), `so` (swap out).
- **IO**: Input/Output statistics. `bi` (blocks received from a block device), `bo` (blocks sent to a block device).
- **System**: System-wide statistics. `in` (interrupts per second), `cs` (context switches per second).
- **CPU**: CPU statistics. `us` (user time), `sy` (system time), `id` (idle time), `wa` (waiting for I/O).

Yeh command aapko system ki health aur performance ko monitor karne me madad karta hai, taaki aap timely action le sakein agar kisi resource ki utilization high hai ya koi performance issue ho raha hai.

> list of commands of linux whcih use to check your system info:

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

Command line tools and terminal applications for various tasks:

### CMD Linux Terminal Applications and Utilities

#### **Command Line Tools to Monitor Linux Performance**
- **`vmstat`** : Monitor system performance (alternative to be searched online)
- **`dstat`** : Versatile resource statistics tool

#### **Graphical User Interface Customization**
- **`lxqt`** : Lightweight Qt desktop environment
- **`Xfce`** : Lightweight desktop environment

#### **Command Help**
- **`--help`** : Display help information for a command
- **`man`** : Manual pages for commands
- **`info`** : Documentation for commands
- **`help`** : Get help for built-in commands

#### **Performance Monitoring and Utilities**
- **`glances`** : Show processes and system details
- **`htop`** : Interactive process viewer
- **`iotop`** : Monitor I/O usage by processes
- **`atop`** : Advanced system and process monitor
- **`bpytop`** : Resource monitoring tool
- **`nmon`** : Performance monitoring tool
- **`sar`** : Collect, report, or save system activity information

#### **Terminal Applications**
- **`eDEX-UI`** : Sci-fi styled terminal emulator
- **`hollywood`** : Terminal simulation with fancy visual effects
- **`sneakers`** : Terminal visualization tool
- **`cmatrix`** : Matrix-style screen saver
- **`bottom`** : Terminal-based resource monitor
- **`mc`** : Midnight Commander, a text-based file manager
- **`xfce4-terminal`** : Lightweight terminal emulator for Xfce
- **`terminator`** : Terminal emulator with multiple resizable panes

#### **Games and Fun Utilities**
- **`asciiquarium`** : ASCII aquarium simulation
- **`lolcat`** : Add colorful effects to text output
- **`cmatrix`** : Terminal screensaver with Matrix-like visuals
- **`ranger`** : Text-based file manager with Vim-like interface
- **`ninvaders`** : ASCII-based Space Invaders game
- **`cowsay`** : Display text with a speech bubble from an ASCII cow

#### **System Information and Storage**
- **`tokei`** : Show statistics about source code
- **`pfetch`** : Display system information
- **`neofetch`** : Show system information with a graphical logo
- **`screenfetch`** : Display system information with a logo
- **`inxi`** : Comprehensive system information tool

#### **Disk Usage Analysis**
- **`ncdu`** : Scan and display disk usage
- **`du`** : Disk usage of files and directories
- **`baobab`** : Disk usage analyzer with a graphical interface

#### **Multiplexers**
- **`tmux`** : Terminal multiplexer allowing multiple windows
- **`screen`** : Terminal multiplexer for managing multiple terminal sessions

#### **Process Monitoring**
- **`ps aux`** : Show all running processes
- **`procs`** : Process viewer with a modern interface
- **`pstree`** : Show processes as a tree
- **`pgrep`** : Look up processes based on name and other attributes

#### **Networking**
- **`nmap`** : Network exploration and security auditing tool
- **`tcpdump`** : Network packet analyzer
- **`netcat`** : Network utility for reading from and writing to network connections

#### **File Transfer and Synchronization**
- **`scp`** : Securely copy files between hosts
- **`rsync`** : Synchronize files and directories between two locations
- **`ftp`** : File transfer protocol client

#### **Text Processing**
- **`awk`** : Text processing and pattern scanning
- **`sed`** : Stream editor for filtering and transforming text
- **`grep`** : Search text using patterns

These tools cover a range of functionalities from system monitoring and management to file transfer and text processing. Feel free to explore and use them as needed!

<hr>
