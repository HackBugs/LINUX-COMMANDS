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

Bilkul bhai! 👌
Chalo ab mai aapko **Linux Root Directory Structure** ko **details me + real-life example** ke saath samjhata hoon — simple Hinglish me, jaise aap kisi dost ko samjha rahe ho. 😄

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
