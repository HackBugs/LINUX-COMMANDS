> #  Linux Root Directory Tree (/)


| Folder           | Purpose (Kya hota hai)                                          |
| ---------------- | --------------------------------------------------------------- |
| `/`              | Root of everything (Linux ka base)                              |
| `/bin`           | Basic commands like `ls`, `cp`, `mv`, etc.                      |
| `/boot`          | Booting files: kernel, grub, initrd                             |
| `/dev`           | Devices like `sda`, `tty`, `usb`, etc.                          |
| `/etc`           | Configuration files (`passwd`, `hosts`, etc.)                   |
| `/home`          | Normal users ka personal data (`/home/shahnawaz`)               |
| `/lib`, `/lib64` | System libraries (.so files) for commands in `/bin` and `/sbin` |
| `/media`         | Auto-mounted devices (like USB, CDs)                            |
| `/mnt`           | Manually mount karne ke liye (external drives, etc.)            |
| `/opt`           | Optional software (custom apps)                                 |
| `/proc`          | Virtual files showing running system info (like CPU, RAM)       |
| `/root`          | Root user ka home folder                                        |
| `/run`           | Runtime process data (temporary info for services)              |
| `/sbin`          | System admin commands (`shutdown`, `reboot`, etc.)              |
| `/srv`           | Server data (like FTP, web data)                                |
| `/sys`           | System hardware info (managed by kernel)                        |
| `/tmp`           | Temporary files (boot ke baad delete ho sakte hain)             |
| `/usr`           | User utilities, programs, libraries (big folder)                |
| `/var`           | Variable data: logs, mails, cache, spool                        |

<hr>

**Linux Root Directory Structure** ko **details me + real-life example**

---

## 📁 `/` – **Root Directory**

> **Root ka papa folder** — sab kuch isi ke andar hota hai.

🔹 Example:

```bash
cd /
```

---

## 📁 `/bin` – **Binary Commands**

> System ke **basic commands** yahin stored hote hain.

🔹 Example:

```bash
/bin/ls     # List files
/bin/cp     # Copy file
/bin/mv     # Move/Rename file
```

✅ Ye commands sab users ke liye available hote hain.

---

## 📁 `/boot` – **Boot Loader Files**

> Jab aapka system **start** hota hai, to yahin se hota hai booting process.

🔹 Example files:

```
/boot/grub/grub.cfg      # GRUB bootloader config
/boot/vmlinuz            # Linux Kernel
```

---

## 📁 `/dev` – **Devices**

> Saare hardware devices ka virtual file yahaan hota hai.

🔹 Examples:

```
/dev/sda     # Hard disk
/dev/tty     # Terminal
/dev/null    # Null device (blackhole)
```

✅ Aap USB lagao to `/dev/sdb` aise dikhega.

---

## 📁 `/etc` – **Configuration Files**

> System ki **setting files** yahaan hoti hain.

🔹 Examples:

```
/etc/hostname          # System ka naam
/etc/hosts             # Local DNS
/etc/passwd            # Users info
/etc/ssh/sshd_config   # SSH server settings
```

---

## 📁 `/home` – **Normal Users ka Ghar**

> Har user ka **personal folder** yahaan banta hai.

🔹 Example:

```
/home/shahnawaz/Documents/
/home/rahul/Desktop/
```

✅ Jab aap `adduser` karte ho, to uska `/home/username` folder banta hai.

---

## 📁 `/lib`, `/lib64` – **Libraries**

> Ye system ke programs ko chalane ke liye zaroori libraries hoti hain (jaise `.so` files).

🔹 Example:

```
/lib/x86_64-linux-gnu/libc.so.6
```

✅ Jab aap `ls`, `cp` jaise command chalate ho, ye libraries help karti hain.

---

## 📁 `/media` – **Auto-Mounted Devices**

> Jab aap **pendrive** ya **CD** lagate ho to vo yahaan mount hoti hai.

🔹 Example:

```
/media/shahnawaz/USB_DRIVE/
```

---

## 📁 `/mnt` – **Manual Mount Point**

> Aap jab manually kisi drive ko mount karte ho to yahaan karte ho.

🔹 Example:

```bash
sudo mount /dev/sdb1 /mnt
```

---

## 📁 `/opt` – **Optional Software**

> Aap koi **third-party software** install karo manually to vo yahaan store hota hai.

🔹 Example:

```
/opt/google/
```

✅ Aap Google Chrome manually install karo to yahin milega.

---

## 📁 `/proc` – **Virtual System Info**

> System ki **live info** yahaan hoti hai — memory, CPU, process, etc.

🔹 Examples:

```
/proc/cpuinfo      # CPU ka info
/proc/meminfo      # RAM usage
/proc/uptime       # System uptime
```

✅ Yeh sab files virtual hoti hain — real me disk pe nahi hoti.

---

## 📁 `/root` – **Root User ka Home Folder**

> `root` user ka private ghar. Normal users ka `/home/username` hota hai, root ka `/root`.

🔹 Example:

```
/root/.bashrc
/root/Downloads/
```

---

## 📁 `/run` – **Runtime Data**

> Jab system start hota hai tab services jo temporary data banati hain, vo yahaan hota hai.

🔹 Example:

```
/run/sshd.pid     # SSH service ka process ID
```

---

## 📁 `/sbin` – **System Binaries (Admin Commands)**

> System admins ke liye commands hote hain (normal user use nahi kar sakta).

🔹 Examples:

```
/sbin/shutdown
/sbin/reboot
/sbin/iptables
```

✅ Root ya sudo user hi run kar sakta hai.

---

## 📁 `/srv` – **Server Data**

> Jab aap FTP, Web, ya kisi server service run karte ho to unka data yahaan hota hai.

🔹 Example:

```
/srv/www/     # Website files
```

---

## 📁 `/sys` – **System Info for Kernel**

> Hardware ke baare me kernel info yahaan store karta hai.

🔹 Example:

```
/sys/class/net/eth0/     # Network device info
```

---

## 📁 `/tmp` – **Temporary Files**

> Temp files, jo automatically delete ho jaati hain reboot ke baad.

🔹 Example:

```
/tmp/tempfile123.tmp
```

---

## 📁 `/usr` – **User Programs**

> Yaha pe aapko milte hain system-wide installed programs, libraries, docs.

```plaintext
/usr
├── bin/       → User-level commands
├── sbin/      → Admin-level commands
├── lib/       → Libraries
├── local/     → Locally compiled programs
├── share/     → Documentation, icons, manuals
```

🔹 Examples:

```
/usr/bin/python3
/usr/lib/libc.so
/usr/share/icons/
```

---

## 📁 `/var` – **Variable Data**

> Jisme frequently change hone wale data hote hain — jaise logs, mails, cache.

```plaintext
/var
├── log/       → System logs
├── mail/      → Mail inbox
├── cache/     → Package cache
├── spool/     → Print/cron jobs
```

🔹 Examples:

```
/var/log/syslog
/var/log/auth.log
/var/cache/apt/
```

---

## 🔚 Final Diagram: (Short Tree with Purpose)

```plaintext
/
├── bin       → Basic commands
├── boot      → Boot files (kernel, grub)
├── dev       → Device files
├── etc       → Configuration files
├── home      → Users' folders
├── lib       → Libraries
├── media     → Auto-mounted drives
├── mnt       → Manual mounts
├── opt       → Optional software
├── proc      → Live system info
├── root      → Root user's home
├── run       → Runtime process info
├── sbin      → System admin commands
├── srv       → Server data
├── sys       → Hardware info (kernel)
├── tmp       → Temporary files
├── usr       → User programs/docs
└── var       → Logs, cache, etc.
```

<hr>

> # Interview Preparation

**Linux Administrator Interview Preparation Guide (Layman + Real-World)**

---

### ✅ 1. **Manage all installed systems and infrastructure**

**Matlab:** Har installed Linux server ka dhyaan rakhna - install, configure, test, aur maintain karna.

**Commands & Examples:**

* Install Ubuntu: Boot ISO se install karte hain
* Set Hostname: `sudo hostnamectl set-hostname server1`
* Configure static IP: `/etc/netplan/*.yaml` file edit karo
* Check system uptime: `uptime`
* Check kernel version: `uname -r`

---

### ✅ 2. **Monitor system performance and manage resources (CPU, Disk, Network)**

**Matlab:** System ka health check karna aur resource ka use control me rakhna.

**Commands:**

* CPU usage: `top`, `htop`
* Memory check: `free -h`
* Disk usage: `df -h`, `du -sh *`
* Network usage: `nload`, `iftop`, `ip -s link`

**Example:**
Jab server slow lage, `top` se check karo kaun sa process CPU zyada le raha hai.

---

### ✅ 3. **Troubleshoot issues (hardware, OS, applications)**

**Matlab:** Jab kuch kaam na kare to uska reason dhoondhna aur fix karna.

**Tools & Commands:**

* Logs dekhne ke liye: `journalctl`, `dmesg`, `/var/log/syslog`
* Check disk health: `smartctl -a /dev/sda`
* Check services: `systemctl status nginx`

**Example:**
Agar website down hai, `systemctl status nginx` se check karo nginx chalu hai ya nahi.

---

### ✅ 4. **Handle system upgrades, backups, and patching**

**Matlab:** Server ko update rakhna, backup lena, aur security patch lagana.

**Commands:**

* Ubuntu update: `sudo apt update && sudo apt upgrade`
* Backup files: `rsync -av /data /backup/`
* Schedule via cron: `crontab -e`
* Check installed packages: `dpkg -l`, `yum list installed`

**Example:**
Daily 2am pe backup chahiye to cron job banate hain.

---

### ✅ 5. **Provide technical support to team members**

**Matlab:** Team ke logon ko help karna jab unka server, access, ya software me problem aaye.

**Real Tasks:**

* User ka password reset: `passwd username`
* User ko sudo dena: `usermod -aG sudo username`
* Mount drive: `mount /dev/sdb1 /mnt`

---

### ✅ 6. **Ensure system security (firewall, IDS)**

**Matlab:** Server secure ho, unauthorized access na ho.

**Commands & Tools:**

* UFW enable: `sudo ufw enable`
* Allow port: `sudo ufw allow 22`
* Disable root SSH login: `/etc/ssh/sshd_config`
* Fail2ban (brute force stop): `sudo apt install fail2ban`

**Example:**
Sirf SSH port open rakhna hai to `ufw allow 22/tcp`

---

### ✅ 7. **Shell Scripting & Automation**

**Matlab:** Daily kaam manually na karke script likh lo jo automatically chale.

**Example Script:**

```bash
#!/bin/bash
# Daily backup script
rsync -av /var/www/ /backup/www_$(date +%F)
```

**Schedule it:**

```bash
crontab -e
0 2 * * * /home/user/scripts/backup.sh
```

---

### 🌟 BONUS: Real-Time Tools to Mention

* Monitoring: `top`, `htop`, `nmon`
* Logs: `journalctl`, `syslog`, `dmesg`
* Backup: `rsync`, `scp`, `tar`
* Security: `ufw`, `iptables`, `fail2ban`
* Scripting: `bash`, `cron`

---




