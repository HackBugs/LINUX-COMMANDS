> ## **Linux administrator** ho with **5 years of experience** aur company-oriented interview Question

### 1. **Basic & System Administration Questions:**
   - **Q1**: How would you troubleshoot a system that is running out of disk space? Which tools and commands would you use?
   - **Q2**: Explain how you would recover the root password on a Linux system.
   - **Q3**: What are the steps to extend a mounted logical volume in LVM without any downtime?
   - **Q4**: Describe how you would find which process is using the most CPU or memory on a system. Which tools would you use?
   - **Q5**: Explain how to schedule regular backups using **cron jobs**. What are the different fields in a cron schedule?
   - **Q6**: How would you upgrade or patch a Linux system while ensuring minimum downtime?
   - **Q7**: What steps do you take to harden a Linux system for security purposes? Name some specific files or configurations you would modify.

### 2. **Networking & Security:**
   - **Q8**: How would you configure a firewall on a Linux system using `iptables` or `firewalld`? Provide an example rule to allow traffic on port 80 (HTTP).
   - **Q9**: Explain how you would diagnose and fix a network issue where the system cannot reach a particular website or IP address.
   - **Q10**: What is SSH port forwarding, and how would you set it up for remote database access securely?
   - **Q11**: How do you implement SSH key-based authentication for multiple servers, and why is it more secure than password-based authentication?
   - **Q12**: Explain how you would secure a web server running on a Linux machine. Mention firewall settings, SELinux, and file permissions.

### 3. **Storage & Filesystem Management:**
   - **Q13**: How do you check and repair a corrupted filesystem on Linux?
   - **Q14**: Can you explain the difference between **ext4**, **XFS**, and **Btrfs** filesystems? Which one would you choose for a large-scale production environment, and why?
   - **Q15**: Describe how you would set up an **NFS server** and configure clients to access shared directories.
   - **Q16**: How would you set up disk quotas for users on a multi-user system?

### 4. **Advanced & Troubleshooting:**
   - **Q17**: A user complains that their application is experiencing high latency. How would you troubleshoot performance issues in a Linux environment?
   - **Q18**: What is the **difference between hard and soft links** in Linux? Provide a real-world use case for each.
   - **Q19**: Explain the use of **strace** and **lsof** in troubleshooting. How would you use them to debug a crashing process?
   - **Q20**: What is the **OOM killer**, and how would you troubleshoot issues caused by it?

### 5. **Automation & Scripting:**
   - **Q21**: How do you automate regular system maintenance tasks? Give examples of some bash scripts you have written to automate system updates, monitoring, or backups.
   - **Q22**: How would you write a script to monitor disk space usage and send an email alert if the usage goes above 80%?
   - **Q23**: Explain how you can use **Ansible** or **Puppet** to manage and deploy configurations across multiple servers.

### 6. **Virtualization & Cloud:**
   - **Q24**: What is the difference between **KVM** and **Docker**? In which scenarios would you use each of them?
   - **Q25**: How would you set up a basic cloud infrastructure on AWS for hosting web applications? Explain the services you would use and why.
   - **Q26**: How do you monitor cloud-based Linux servers for performance and uptime? What tools or services do you recommend?

### 7. **Backup & Disaster Recovery:**
   - **Q27**: What are your best practices for backing up critical data in a Linux environment? How would you implement a disaster recovery plan for a Linux server?
   - **Q28**: Explain how you would configure a **RAID** array on Linux. What are the differences between RAID 0, 1, 5, and 10, and when would you use each?

### 8. **Kernel & System Tuning:**
   - **Q29**: How do you update the kernel in a Linux system, and how do you ensure it boots into the new kernel?
   - **Q30**: How would you optimize a Linux system for better performance? Explain kernel tuning parameters like **swappiness**, **file descriptor limits**, or **CPU scheduling**.

### 9. **Monitoring & Logs:**
   - **Q31**: How do you monitor Linux systems for performance and health? Which monitoring tools (e.g., **Nagios**, **Prometheus**, **Grafana**) have you used, and how did you set them up?
   - **Q32**: Explain how you would troubleshoot a system crash or kernel panic using logs. Which log files or commands would you look at?
   
### 10. **DevOps & CI/CD Integration**:
   - **Q33**: How have you integrated Linux systems with CI/CD pipelines (e.g., Jenkins)? Explain the setup for deploying applications from GitHub to production using automation.
   - **Q34**: How would you use containers (e.g., **Docker**) in a Linux environment for testing and deployment?

---

### Scenario-Based Questions:
   - **Q35**: You are managing a web server, and it's suddenly inaccessible. Walk through how you would troubleshoot the issue from both a network and application perspective.
   - **Q36**: Your company’s database server is running slow. What steps would you take to identify and resolve the issue?
   - **Q37**: An application running on a production server crashes occasionally without giving an error. How would you troubleshoot and identify the root cause?

These questions focus on advanced topics in Linux administration that require hands-on experience, problem-solving, and an understanding of system-level operations.

------

>  ## Q -1 **LVM** stands for **Logical Volume Manager**. It is a tool used in Linux-based systems for managing disk storage. LVM allows for flexible management of storage by abstracting the physical layout of the storage devices, making it easier to resize, add, or remove storage volumes without downtime.

### Key Concepts of LVM:

1. **Physical Volumes (PVs)**: These are the physical hard drives or partitions that LVM can use. A physical volume could be an entire disk or a specific partition.
   
2. **Volume Groups (VGs)**: A volume group is a collection of physical volumes that are combined into a single storage pool. You can allocate space from this pool to create logical volumes.

3. **Logical Volumes (LVs)**: Logical volumes are the actual partitions created from the volume group that can be used by the operating system to store files. These can be resized easily, unlike traditional partitions.

4. **Flexibility**: LVM allows for dynamic resizing of volumes. You can expand or shrink volumes, add new physical disks, and manage storage without worrying about hardware constraints.

### Why Use LVM?

- **Dynamic Resizing**: You can increase or decrease the size of logical volumes without restarting the system. This is helpful in production environments where downtime is not acceptable.
  
- **Snapshotting**: LVM allows you to take snapshots of volumes, which can be useful for backups or testing without affecting the running system.

- **Efficient Use of Storage**: Since LVM pools together physical storage, it allows for better utilization of disk space by allocating storage as needed.

- **Add or Remove Disks Easily**: With LVM, you can add more storage devices (physical volumes) to a volume group and extend your logical volumes as needed.

### Basic LVM Workflow:

1. **Create Physical Volume**: You mark a disk or partition as a physical volume (PV) that can be used by LVM.

2. **Create Volume Group**: Combine multiple physical volumes into a single volume group (VG), which is like a pool of storage.

3. **Create Logical Volume**: Allocate space from the volume group to create logical volumes (LVs). These are used like regular partitions.

4. **Mount and Use**: Mount the logical volume and start using it for storing data.

### Example Commands:

1. **Create Physical Volume**:

   ```bash
   sudo pvcreate /dev/sdb
   ```

   This makes `/dev/sdb` available for LVM.

2. **Create Volume Group**:

   ```bash
   sudo vgcreate my_volume_group /dev/sdb
   ```

   This combines `/dev/sdb` into a volume group called `my_volume_group`.

3. **Create Logical Volume**:

   ```bash
   sudo lvcreate -L 10G -n my_logical_volume my_volume_group
   ```

   This creates a 10GB logical volume called `my_logical_volume` from the volume group `my_volume_group`.

4. **Format the Logical Volume**:

   ```bash
   sudo mkfs.ext4 /dev/my_volume_group/my_logical_volume
   ```

   This formats the logical volume with the ext4 filesystem.

5. **Mount the Logical Volume**:

   ```bash
   sudo mount /dev/my_volume_group/my_logical_volume /mnt/mydata
   ```

   This mounts the logical volume to `/mnt/mydata` so it can be used.

### Example Use Case:
Suppose you have a server running out of storage space. Instead of repartitioning the hard drive and worrying about losing data, you can use LVM to add a new hard drive to your server and expand the existing logical volume without any downtime.

### LVM Components:

1. **Physical Volume (PV)**: Raw disks or partitions.
2. **Volume Group (VG)**: Pool of storage made up of physical volumes.
3. **Logical Volume (LV)**: Flexible partitions created from the volume group, which can be mounted and used.

### Benefits of LVM:

- **Scalability**: Easy to add more storage.
- **Snapshots**: Create backup snapshots of volumes.
- **Flexible Resizing**: Logical volumes can be resized without system downtime.
- **Storage Pooling**: Multiple physical drives can be combined into a single volume.

LVM is a powerful tool, especially in environments where you need flexible, efficient, and scalable storage management.

------

> ## Q - 1 command list covering all essential LVM tasks, from setting up physical volumes to managing logical volumes:

```bash
# 1. Initialize a disk as a Physical Volume (PV)
sudo pvcreate /dev/sdX              # Replace /dev/sdX with your disk, e.g., /dev/sdb

# 2. Create a Volume Group (VG) from one or more Physical Volumes
sudo vgcreate my_volume_group /dev/sdX

# 3. Create a Logical Volume (LV) from the Volume Group
sudo lvcreate -L 10G -n my_logical_volume my_volume_group   # Creates a 10GB LV named "my_logical_volume"

# 4. Format the Logical Volume with a filesystem (e.g., ext4)
sudo mkfs.ext4 /dev/my_volume_group/my_logical_volume

# 5. Mount the Logical Volume
sudo mkdir -p /mnt/mydata                                   # Create mount point if it doesn’t exist
sudo mount /dev/my_volume_group/my_logical_volume /mnt/mydata

# 6. Extend Physical Volume (use if the disk has been resized or new space added)
sudo pvresize /dev/sdX

# 7. Extend Logical Volume to use available free space in the Volume Group
sudo lvextend -l +100%FREE /dev/my_volume_group/my_logical_volume

# 8. Resize the Filesystem to use the new Logical Volume size
# For ext4 filesystem:
sudo resize2fs /dev/my_volume_group/my_logical_volume

# For xfs filesystem:
sudo xfs_growfs /dev/my_volume_group/my_logical_volume

# 9. Display current Physical Volumes, Volume Groups, and Logical Volumes
sudo pvs    # Lists Physical Volumes
sudo vgs    # Lists Volume Groups
sudo lvs    # Lists Logical Volumes

# 10. Take a Snapshot of a Logical Volume (useful for backups)
sudo lvcreate -L 1G -s -n my_snapshot /dev/my_volume_group/my_logical_volume   # Creates a 1GB snapshot

# 11. Remove a Logical Volume
sudo lvremove /dev/my_volume_group/my_logical_volume

# 12. Remove a Volume Group
sudo vgremove my_volume_group

# 13. Remove a Physical Volume (after removing LV and VG)
sudo pvremove /dev/sdX
```

### Key Notes:
- **Replace placeholders** (`/dev/sdX`, `my_volume_group`, `my_logical_volume`) with actual names used in your setup.
- Always ensure you have backups before modifying storage configurations, especially when resizing or removing volumes.

----------

> ### Q - 2 To recover the root password on a Linux system, you can follow these steps. This process involves booting into single-user mode or emergency mode, which allows you to access the system as a superuser without requiring a password. Here’s a detailed guide on how to do it:

---

### Steps to Recover the Root Password on a Linux System

1. **Reboot the System**:
   - Restart your system, and during boot, press the appropriate key (usually `Esc`, `Shift`, or `E`) to access the GRUB boot menu.

2. **Edit the GRUB Entry**:
   - In the GRUB menu, use the arrow keys to highlight the default boot option (usually the first one).
   - Press `e` to edit the selected boot entry.

3. **Modify the Boot Parameters**:
   - Locate the line that starts with `linux` and ends with `quiet` or `rhgb quiet`.
   - Delete `quiet` and `rhgb` if they’re present, and replace them with `rw init=/bin/bash` (or `init=/bin/sh` on some distributions).
   - This change tells the system to boot directly into a shell without loading all other services.

   Example:
   ```bash
   linux /boot/vmlinuz-xxxx root=UUID=xxxx ro quiet splash
   ```
   Change to:
   ```bash
   linux /boot/vmlinuz-xxxx root=UUID=xxxx rw init=/bin/bash
   ```

4. **Boot into Single-User Mode**:
   - After making the changes, press `Ctrl + X` or `F10` to boot with the modified entry.

5. **Remount the Root Filesystem**:
   - Once you’re in single-user mode, the filesystem is mounted as read-only by default. You need to remount it as read-write to make changes.
   - Run the following command:
     ```bash
     mount -o remount,rw /
     ```

6. **Change the Root Password**:
   - Now, set a new root password with the `passwd` command:
     ```bash
     passwd root
     ```
   - Enter the new password when prompted, and confirm it.

7. **Reboot the System**:
   - Remount the filesystem as read-only again and reboot:
     ```bash
     mount -o remount,ro /
     exec /sbin/reboot
     ```
   - The system will now reboot with the updated root password.

---

### Summary of Commands
1. **Edit GRUB entry**: `linux /boot/vmlinuz-xxxx root=UUID=xxxx rw init=/bin/bash`
2. **Remount root filesystem**: `mount -o remount,rw /`
3. **Set new root password**: `passwd root`
4. **Reboot system**: `exec /sbin/reboot`

---

### Important Notes
- This recovery process requires physical or console access to the system.
- If the system is protected by GRUB password protection, you’ll need the GRUB password to edit the boot parameters.
- Ensure to follow security protocols when performing password recovery to maintain the system’s integrity.

