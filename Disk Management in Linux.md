> ## Here's a comprehensive list of essential disk management commands in Linux, covering a variety of tasks from viewing disk usage to managing partitions, file systems, and disks:

### 1. **Viewing Disk Information**

- **`lsblk`** – Lists all available block devices (disks and partitions) in a tree format.
  ```bash
  lsblk
  ```

- **`fdisk -l`** – Shows detailed information about all disks and partitions.
  ```bash
  sudo fdisk -l
  ```

- **`df -h`** – Displays disk usage of mounted filesystems in human-readable format.
  ```bash
  df -h
  ```

- **`du -sh /path/to/dir`** – Displays the total disk usage of a specific directory.
  ```bash
  du -sh /home
  ```

- **`ls -lh /dev/disk/by-id/`** – Lists disks with their unique identifiers.
  ```bash
  ls -lh /dev/disk/by-id/
  ```

### 2. **Managing Partitions**

- **`fdisk /dev/sdX`** – Interactive partition editor for MBR disks (replace `X` with the drive letter).
  ```bash
  sudo fdisk /dev/sda
  ```

- **`parted /dev/sdX`** – Interactive partition editor supporting both MBR and GPT disks.
  ```bash
  sudo parted /dev/sda
  ```

- **`lsblk -f`** – Displays filesystems on partitions, helping identify unmounted partitions.
  ```bash
  lsblk -f
  ```

- **`mkfs.ext4 /dev/sdXY`** – Formats a partition with the ext4 filesystem.
  ```bash
  sudo mkfs.ext4 /dev/sda1
  ```

- **`mkfs.xfs /dev/sdXY`** – Formats a partition with the XFS filesystem.
  ```bash
  sudo mkfs.xfs /dev/sda1
  ```

### 3. **Mounting and Unmounting**

- **`mount /dev/sdXY /mnt`** – Mounts a specific partition to `/mnt` (replace `XY` with partition).
  ```bash
  sudo mount /dev/sda1 /mnt
  ```

- **`umount /dev/sdXY`** – Unmounts a partition.
  ```bash
  sudo umount /dev/sda1
  ```

- **`mount -o loop disk_image.iso /mnt`** – Mounts an ISO disk image to `/mnt`.
  ```bash
  sudo mount -o loop /path/to/image.iso /mnt
  ```

- **`findmnt`** – Displays all mounted filesystems in a tree format.
  ```bash
  findmnt
  ```

### 4. **Disk Usage and Space Analysis**

- **`du -ah /path/to/dir`** – Shows disk usage for all files and folders in a directory.
  ```bash
  du -ah /home/user
  ```

- **`df -i`** – Displays inode usage for each mounted filesystem.
  ```bash
  df -i
  ```

- **`ncdu`** – Interactive disk usage analyzer.
  ```bash
  sudo apt install ncdu
  ncdu /home
  ```

### 5. **Swap Space Management**

- **`swapon --show`** – Lists all active swap partitions and files.
  ```bash
  swapon --show
  ```

- **`mkswap /dev/sdXY`** – Creates a swap space on a specified partition.
  ```bash
  sudo mkswap /dev/sda2
  ```

- **`swapon /dev/sdXY`** – Activates swap on a partition or file.
  ```bash
  sudo swapon /dev/sda2
  ```

- **`swapoff /dev/sdXY`** – Deactivates swap on a partition or file.
  ```bash
  sudo swapoff /dev/sda2
  ```

### 6. **LVM (Logical Volume Manager)**

- **`pvcreate /dev/sdXY`** – Initializes a disk partition as a physical volume.
  ```bash
  sudo pvcreate /dev/sdb1
  ```

- **`vgcreate volume_group_name /dev/sdXY`** – Creates a volume group with the specified physical volume.
  ```bash
  sudo vgcreate my_vg /dev/sdb1
  ```

- **`lvcreate -L 10G -n logical_volume_name volume_group_name`** – Creates a logical volume of 10GB.
  ```bash
  sudo lvcreate -L 10G -n my_lv my_vg
  ```

- **`lvextend -L +5G /dev/volume_group_name/logical_volume_name`** – Extends the logical volume by 5GB.
  ```bash
  sudo lvextend -L +5G /dev/my_vg/my_lv
  ```

### 7. **RAID Management**

- **`mdadm --create`** – Creates a new RAID array.
  ```bash
  sudo mdadm --create /dev/md0 --level=1 --raid-devices=2 /dev/sda /dev/sdb
  ```

- **`cat /proc/mdstat`** – Shows the status of RAID arrays.
  ```bash
  cat /proc/mdstat
  ```

### 8. **File System Maintenance**

- **`fsck /dev/sdXY`** – Checks and repairs filesystem errors on a partition.
  ```bash
  sudo fsck /dev/sda1
  ```

- **`tune2fs -l /dev/sdXY`** – Shows detailed information about an ext2/ext3/ext4 filesystem.
  ```bash
  sudo tune2fs -l /dev/sda1
  ```

- **`resize2fs /dev/sdXY`** – Resizes an ext2/ext3/ext4 filesystem.
  ```bash
  sudo resize2fs /dev/sda1
  ```

### 9. **Disk Label Management**

- **`blkid`** – Lists all filesystems with their UUIDs.
  ```bash
  blkid
  ```

- **`e2label /dev/sdXY label_name`** – Sets or changes the label of an ext2/ext3/ext4 partition.
  ```bash
  sudo e2label /dev/sda1 mylabel
  ```

- **`parted /dev/sdX name 1 'mylabel'`** – Sets a name for the first partition on a disk.
  ```bash
  sudo parted /dev/sda name 1 'mylabel'
  ```

### 10. **Disk Encryption**

- **`cryptsetup luksFormat /dev/sdXY`** – Sets up LUKS encryption on a partition.
  ```bash
  sudo cryptsetup luksFormat /dev/sda1
  ```

- **`cryptsetup open /dev/sdXY encrypted_volume`** – Opens and mounts an encrypted partition.
  ```bash
  sudo cryptsetup open /dev/sda1 encrypted_volume
  ```

### Summary

These commands cover the majority of disk management tasks in Linux. Make sure to use `sudo` where needed for administrative tasks, as many of these commands require root permissions. Always double-check the disk or partition before running potentially destructive commands like `fdisk`, `mkfs`, or `cryptsetup`.

---------

> ## Sure, here are just the commands in the requested order:

```bash
# 06:10 - lsblk
lsblk

# 08:54 - fdisk
sudo fdisk /dev/sdX

# 10:30 - dmesg
dmesg | tail

# 11:39 - lshw
sudo lshw -C disk

# 12:07 - lsscsi
lsscsi

# 15:44 - badblocks
sudo badblocks -sv /dev/sdX

# 20:08 - dd
sudo dd if=/dev/sdX of=/dev/sdY bs=4M

# 23:26 - Adding disk
sudo pvcreate /dev/sdX
sudo vgcreate vg_name /dev/sdX
sudo lvcreate -L 10G -n lv_name vg_name

# 25:20 - Manual scan
sudo partprobe /dev/sdX

# 30:00 - partprobe
sudo partprobe

# 31:38 - Creating partition
sudo fdisk /dev/sdX

# 40:31 - Test mounting without filesystem
sudo mount /dev/sdX /mnt

# 42:24 - mkfs
sudo mkfs.ext4 /dev/sdX1

# 44:00 - Mount to directory
sudo mount /dev/sdX1 /path/to/mount_dir

# 46:14 - Checking limitations
df -h
``` 

Replace `/dev/sdX` and `/path/to/mount_dir` with your actual disk identifiers and mount points.

------

> ## The command in the image is:

```bash
ls /sys/class/scsi_host/ | while read host; do echo "- - -" > /sys/class/scsi_host/$host/scan; done
```

This command scans all SCSI hosts to detect new disks or storage devices that have been added without rebooting.


> ## The command in the image is:

```bash
for x in `ls /sys/class/scsi_host/`; do echo "-----$x Scanned-----"; echo "- - -" > /sys/class/scsi_host/$x/scan; done
```

This command iterates over each SCSI host in `/sys/class/scsi_host/`, prints a message indicating that the host is being scanned, and then forces a rescan of the SCSI bus for each host to detect new storage devices.

> ## Here is the organized list with categories:

---

### Software and Applications
- **jbox** - Middleware
- **PostgreSQL** - Database
- **WAR file** - Web application archive (Deployment on servers)
- **dclear** - Clear/deploy configurations (possibly custom usage)

---

### Disk and Memory Commands

#### Basic Disk and Memory Commands
- `lsblk` - List all block devices
- `lsblk -f` - List block devices with filesystem information
- `free -m` - Display memory usage in megabytes
- `cat /proc/partitions` - List partitions

---

#### Disk Partitioning and Manipulation
- `fdisk` - Partition a disk (supports MBR)
  - `fdisk -l` - List all partitions
  - `fdisk /dev/sda` - Enter `fdisk` for `/dev/sda` (use `m` for help)
- `gdisk -l /dev/sda` - List partitions using `gdisk` (supports GPT)
- `parted` - Manage disk partitions (supports both MBR and GPT)
- `partprobe` - Inform the OS of partition table changes

---

#### Disk Checking and Formatting
- `badblocks` - Check for bad sectors on a disk
- `dd` - Low-level data copying and backup (can be used for data wiping or creating disk images)

---

### Disk Identification and Filesystem Commands
- `blkid` - Display block device attributes
- `dmesg` - Kernel message buffer (useful for hardware-related logs)
- `lshw` - Display detailed hardware information
- `lsscsi` - List SCSI devices

---

### Partitioning Types and Tools
- **MBR** (Master Boot Record) - BIOS-based, allows up to 4 primary partitions, uses `fdisk`
- **GPT** (GUID Partition Table) - UEFI-based, supports up to 128 primary partitions, uses `gdisk`
  - `fdisk` - Supports MBR
  - `gdisk` - Supports GPT
  - `parted` - Supports both MBR and GPT

-----------

> ## Here’s an organized list of essential networking tools and commands in Linux:

---

### Basic Networking Commands
- `ifconfig` - Display or configure network interfaces (older command, replaced by `ip` command).
- `ip a` - Display IP addresses and network interfaces.
- `ip link` - Display and modify network interface states.
- `ip route` - Display or manipulate the IP routing table.
- `ip addr add <ip_address>/24 dev <interface>` - Add an IP address to a network interface.

---

### Network Testing and Diagnostics
- `ping <hostname/IP>` - Check connectivity to a host.
- `traceroute <hostname/IP>` - Trace the path packets take to a network host.
- `tracepath <hostname/IP>` - Similar to `traceroute`, but doesn’t require superuser privileges.
- `mtr <hostname/IP>` - Network diagnostic tool combining `ping` and `traceroute`.
- `netstat -tuln` - Display open ports and listening services.
- `ss -tuln` - Modern replacement for `netstat` (displays network socket information).
- `nc -zv <hostname/IP> <port>` - Check if a specific port is open on a host (`netcat` tool).
- `telnet <hostname/IP> <port>` - Test connectivity to specific ports (useful for testing mail servers, etc.).
  
---

### DNS and Name Resolution
- `nslookup <domain>` - Query DNS to resolve domain names.
- `dig <domain>` - Detailed DNS lookup and debugging.
- `host <domain>` - Simple DNS lookup.
- `resolvectl` - Check and configure DNS resolver on systemd-based systems.

---

### Network Monitoring and Analysis
- `tcpdump` - Capture and analyze network packets.
  - Example: `tcpdump -i <interface>` - Capture packets on a specific interface.
- `wireshark` - GUI tool for network packet capture and analysis.
- `iftop` - Monitor bandwidth usage per connection in real-time.
- `nload` - Real-time network traffic visualization.
- `vnstat` - Monitor and log network traffic data over time.

---

### Managing Network Connections
- `nmcli` - NetworkManager command-line tool for managing network connections.
  - Example: `nmcli device status` - Show network interface status.
  - Example: `nmcli con up <connection_name>` - Bring up a network connection.
- `nmtui` - Text-based user interface for NetworkManager.
- `systemctl restart network` - Restart network service (for non-NetworkManager-managed services).

---

### Network Configuration Files
- `/etc/hosts` - Static table lookup for hostnames.
- `/etc/resolv.conf` - Configure DNS nameservers.
- `/etc/sysconfig/network-scripts/ifcfg-<interface>` - Network configuration file for specific interfaces (on Red Hat-based systems).
- `/etc/network/interfaces` - Network configuration file (on Debian-based systems).

---

### Firewall and Security
- `iptables` - Command-line firewall (older tool, now replaced by `nftables` on many systems).
  - Example: `iptables -L` - List firewall rules.
  - Example: `iptables -A INPUT -p tcp --dport 22 -j ACCEPT` - Allow SSH traffic.
- `nft` - Modern firewall management tool, replacing `iptables`.
  - Example: `nft list ruleset` - List all firewall rules.
- `ufw` - Simplified firewall tool (used on Ubuntu).
  - Example: `ufw status` - Check firewall status.
  - Example: `ufw allow <port>` - Allow traffic on a specific port.
- `firewalld` - Dynamic firewall manager on Red Hat-based systems.
  - Example: `firewall-cmd --list-all` - List all firewall rules.
  - Example: `firewall-cmd --add-port=<port>/tcp --permanent` - Open a port permanently.

---

### Network File Transfer
- `scp <source> <user>@<host>:<destination>` - Secure copy files over SSH.
- `sftp <user>@<host>` - Secure File Transfer Protocol over SSH.
- `rsync -avz <source> <user>@<host>:<destination>` - Synchronize files/directories over the network.
- `curl <URL>` - Download or transfer data from/to a server.
- `wget <URL>` - Download files from the web.

---

### SSH (Secure Shell)
- `ssh <user>@<host>` - Log into a remote machine.
- `ssh-keygen` - Generate SSH keys for password-less login.
- `ssh-copy-id <user>@<host>` - Copy SSH key to a remote server for password-less login.
- `ssh -L <local_port>:<remote_host>:<remote_port> <user>@<host>` - Set up SSH tunneling (port forwarding).

---

### Network Services and Ports
- `systemctl status <service>` - Check the status of a network service.
- `systemctl start <service>` - Start a network service.
- `systemctl stop <service>` - Stop a network service.
- `lsof -i :<port>` - List processes using a specific port.
- `fuser -k <port>/tcp` - Kill the process occupying a specific port.

---

### Network Interface Management
- `ethtool <interface>` - Display or change Ethernet device settings.
- `ifdown <interface>` - Disable a network interface.
- `ifup <interface>` - Enable a network interface.
- `iwconfig` - Configure wireless network interfaces.

---

### Network Automation Tools
- **Ansible** - Automation tool for configuring network devices and servers.
- **Chef** - Infrastructure as code tool to automate network and server configurations.
- **Terraform** - Infrastructure as code tool for managing network resources in cloud environments.

> ## Here's an organized list of essential Linux commands for gathering system information:

---

### General System Information
- `uname -a` - Display all kernel and system information.
- `hostnamectl` - Show detailed system information (hostname, OS version, architecture).
- `lsb_release -a` - Display Linux distribution information (useful on Debian-based systems).
- `cat /etc/os-release` - Display operating system information.
- `uptime` - Show how long the system has been running and load averages.
- `dmesg | less` - Kernel ring buffer messages (useful for diagnosing hardware issues).

---

### CPU Information
- `lscpu` - Display CPU architecture information.
- `cat /proc/cpuinfo` - Detailed information about each CPU core.
- `nproc` - Show the number of processing units available.
- `top` or `htop` - Real-time view of CPU usage by processes.
- `mpstat` - CPU usage statistics (requires `sysstat` package).
  
---

### Memory Information
- `free -h` - Display free and used memory in human-readable format.
- `cat /proc/meminfo` - Detailed information about memory usage.
- `vmstat` - Memory usage, CPU, and I/O stats.
  
---

### Disk and Filesystem Information
- `df -h` - Show disk usage by filesystem in human-readable format.
- `lsblk` - List all block devices (disks, partitions, etc.).
- `fdisk -l` - List all available disks and their partitions.
- `blkid` - List block device attributes (UUID, type, etc.).
- `parted -l` - Display partition layout for all devices.
- `du -sh <directory>` - Show disk usage for a specific directory.
- `ls /sys/class/scsi_host/` - View SCSI hosts (useful for detecting new disks).
- `echo "- - -" > /sys/class/scsi_host/host#/scan` - Rescan SCSI bus for new storage devices.

---

### Hardware Information
- `lshw` - Detailed hardware information (may require root privileges).
- `lscpi` - Display information about PCI devices.
- `lsusb` - List all USB devices connected to the system.
- `dmidecode` - Display DMI/SMBIOS (hardware) information (requires root).
  - Example: `dmidecode -t memory` - Show information about RAM.
- `inxi -F` - Brief overview of system hardware (requires `inxi` package).

---

### Network Information
- `ip a` - Display network interfaces and IP addresses.
- `ifconfig` - Network configuration and interface status (older command).
- `nmcli device status` - Show network interface status (NetworkManager).
- `ip route` - Display the routing table.
- `ss -tuln` - Show listening ports and associated services.
- `netstat -tuln` - Display active connections and listening ports.

---

### I/O and Storage Information
- `iostat` - CPU and I/O statistics (requires `sysstat` package).
- `lsblk -f` - Show all block devices with filesystem information.
- `smartctl -a /dev/sdX` - Check the health of a disk (requires `smartmontools`).
- `badblocks -v /dev/sdX` - Search for bad sectors on a disk (use with caution).
  
---

### GPU Information
- `lspci | grep -i vga` - Display information about the graphics card.
- `glxinfo | grep "OpenGL renderer"` - Show GPU information (requires `mesa-utils`).
- `nvidia-smi` - NVIDIA GPU information (requires NVIDIA drivers).

---

### System Load and Performance
- `top` - Real-time view of system processes, memory, and CPU usage.
- `htop` - Enhanced version of `top` with better visualization (requires installation).
- `vmstat` - Show system performance and memory usage statistics.
- `sar` - Historical system activity report (requires `sysstat` package).
- `uptime` - Show system load averages over the past 1, 5, and 15 minutes.
- `ps aux` - Display information about all running processes.

---

### System Logs
- `journalctl` - View systemd logs (useful for debugging).
  - Example: `journalctl -u <service_name>` - View logs for a specific service.
- `cat /var/log/syslog` - View system log file (Debian-based systems).
- `cat /var/log/messages` - View system log file (Red Hat-based systems).
- `dmesg` - Show kernel-related logs, including hardware information.

---

### Battery and Power Information (for Laptops)
- `upower -i /org/freedesktop/UPower/devices/battery_BAT0` - Show detailed battery information.
- `acpi` - Display battery status and other power information (requires `acpi` package).

---

### Temperature and Fan Information
- `sensors` - Display system temperatures (requires `lm-sensors` package).
  - Run `sudo sensors-detect` first to configure.
- `hddtemp /dev/sdX` - Check the temperature of a hard drive (requires `hddtemp`).

---

### Miscellaneous
- `lsmod` - List all loaded kernel modules.
- `modinfo <module_name>` - Show information about a specific kernel module.
- `systemctl list-units --type=service` - List all active services.
- `systemctl status <service_name>` - Check the status of a specific service.
  
----------

> ## Here are the essential Linux commands to check the status of services, manage packages, and stop or kill running services and processes:

---

### Service Status and Management

1. **Check the Status of a Service**  
   ```bash
   systemctl status <service_name>
   ```
   Example: `systemctl status nginx`

2. **Start a Service**  
   ```bash
   systemctl start <service_name>
   ```
   Example: `systemctl start apache2`

3. **Stop a Service**  
   ```bash
   systemctl stop <service_name>
   ```
   Example: `systemctl stop sshd`

4. **Restart a Service**  
   ```bash
   systemctl restart <service_name>
   ```
   Example: `systemctl restart mysql`

5. **Enable a Service (start at boot)**  
   ```bash
   systemctl enable <service_name>
   ```
   Example: `systemctl enable docker`

6. **Disable a Service (do not start at boot)**  
   ```bash
   systemctl disable <service_name>
   ```
   Example: `systemctl disable bluetooth`

7. **List All Active Services**  
   ```bash
   systemctl list-units --type=service
   ```

8. **List All Enabled Services**  
   ```bash
   systemctl list-unit-files --type=service | grep enabled
   ```

---

### Package Management (Status, Installation, and Removal)

**For Debian-based Systems (e.g., Ubuntu, Debian)**

1. **Check if a Package is Installed**  
   ```bash
   dpkg -l | grep <package_name>
   ```
   Example: `dpkg -l | grep nginx`

2. **Install a Package**  
   ```bash
   sudo apt install <package_name>
   ```
   Example: `sudo apt install apache2`

3. **Remove a Package**  
   ```bash
   sudo apt remove <package_name>
   ```
   Example: `sudo apt remove nginx`

4. **Update All Packages**  
   ```bash
   sudo apt update && sudo apt upgrade
   ```

**For Red Hat-based Systems (e.g., RHEL, CentOS, Fedora)**

1. **Check if a Package is Installed**  
   ```bash
   rpm -qa | grep <package_name>
   ```
   Example: `rpm -qa | grep httpd`

2. **Install a Package**  
   ```bash
   sudo yum install <package_name>
   ```
   Example: `sudo yum install nginx`

3. **Remove a Package**  
   ```bash
   sudo yum remove <package_name>
   ```
   Example: `sudo yum remove nginx`

4. **Update All Packages**  
   ```bash
   sudo yum update
   ```

---

### Process Management

1. **List All Running Processes**  
   ```bash
   ps aux
   ```

2. **Find a Process by Name**  
   ```bash
   ps aux | grep <process_name>
   ```
   Example: `ps aux | grep apache`

3. **Kill a Process by PID (Process ID)**  
   ```bash
   kill <pid>
   ```
   Example: `kill 1234`

4. **Force Kill a Process by PID**  
   ```bash
   kill -9 <pid>
   ```
   Example: `kill -9 1234`

5. **Kill All Processes by Name**  
   ```bash
   pkill <process_name>
   ```
   Example: `pkill apache`

6. **Show System Resource Usage by Process (Top Command)**  
   ```bash
   top
   ```
   or
   ```bash
   htop
   ```

---

### Network Services

1. **List All Listening Ports and Services**  
   ```bash
   ss -tuln
   ```

2. **Kill a Service Listening on a Specific Port**  
   Find the process ID:
   ```bash
   lsof -i:<port_number>
   ```
   Example: `lsof -i:8080`

   Kill the process:
   ```bash
   kill <pid>
   ```

---

These commands provide control over services and processes, allowing you to start, stop, and manage services, and check or kill running processes as needed.

> ## Here are the commands to enable and disable the firewall on Linux, depending on your firewall tool.

---

### Using `firewalld` (common on RHEL, CentOS, Fedora)

1. **Enable Firewall**  
   ```bash
   sudo systemctl enable firewalld
   sudo systemctl start firewalld
   ```

2. **Disable Firewall**  
   ```bash
   sudo systemctl stop firewalld
   sudo systemctl disable firewalld
   ```

3. **Check Firewall Status**  
   ```bash
   sudo systemctl status firewalld
   ```

4. **Reload Firewall Rules**  
   ```bash
   sudo firewall-cmd --reload
   ```

---

### Using `ufw` (common on Ubuntu, Debian)

1. **Enable Firewall**  
   ```bash
   sudo ufw enable
   ```

2. **Disable Firewall**  
   ```bash
   sudo ufw disable
   ```

3. **Check Firewall Status**  
   ```bash
   sudo ufw status
   ```

4. **Reload Firewall Rules**  
   ```bash
   sudo ufw reload
   ```

---

These commands allow you to enable or disable the firewall and check its status, whether you're using `firewalld` or `ufw`.
