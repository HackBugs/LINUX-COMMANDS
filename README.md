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
