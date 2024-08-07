
> ## Usefull Commands to check program, services, ports, active service and more

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

If you want to list all installed services that are managed by `systemd` on your Linux system, you can use `systemctl` commands. Here's how you can do it:

### **List All Installed Services Managed by `systemd`**

1. **List All Services**

   To see a list of all services, including those that are loaded but not currently active:

   ```bash
   systemctl list-unit-files --type=service
   ```

   This command will show all unit files for services, including their state (enabled, disabled, etc.).

2. **List All Active Services**

   To see services that are currently active (running):

   ```bash
   systemctl list-units --type=service --state=active
   ```

3. **List All Inactive Services**

   To list services that are not currently running:

   ```bash
   systemctl list-units --type=service --state=inactive
   ```

4. **List All Failed Services**

   To see services that have failed:

   ```bash
   systemctl list-units --type=service --state=failed
   ```

5. **Check Service Status**

   To get the status of a specific service (e.g., `nginx`):

   ```bash
   systemctl status nginx
   ```

### **List Installed Programs**

If you want to see all installed programs (not just services), you need to use package management commands rather than `systemctl`. Here’s how you can list installed packages using various package managers:

- **Debian/Ubuntu-based systems (using `dpkg`):**

  ```bash
  dpkg --list
  ```

  or for a more concise view:

  ```bash
  dpkg -l | grep '^ii'
  ```

- **Red Hat/CentOS-based systems (using `rpm`):**

  ```bash
  rpm -qa
  ```

- **Fedora systems (using `dnf`):**

  ```bash
  dnf list installed
  ```

- **Arch Linux (using `pacman`):**

  ```bash
  pacman -Q
  ```

### **Summary**

- **`systemctl`**: Use to manage and list services managed by `systemd`.
- **Package Managers**: Use commands like `dpkg --list`, `rpm -qa`, `dnf list installed`, or `pacman -Q` to list installed programs.

This approach will help you manage both services and installed programs on your system.
