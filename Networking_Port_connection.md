
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

<hr>

To see all the ports currently in use on your Ubuntu system, you can use the `netstat`, `ss`, or `lsof` commands. Here are different ways to check all busy ports:

### Using `ss` Command

`ss` is a modern replacement for `netstat` and provides detailed information about ports in use.

```bash
sudo ss -tulnp
```

- `-t`: Show TCP ports.
- `-u`: Show UDP ports.
- `-l`: Show only listening ports.
- `-n`: Show numerical addresses instead of resolving hostnames.
- `-p`: Show the process using the port.

### Using `netstat` Command

If `netstat` is installed on your system, you can use it to view all busy ports.

```bash
sudo netstat -tulnp
```

- `-t`: Show TCP ports.
- `-u`: Show UDP ports.
- `-l`: Show only listening ports.
- `-n`: Show numerical addresses.
- `-p`: Show the process using the port.

### Using `lsof` Command

`lsof` lists open files and the ports associated with them.

```bash
sudo lsof -i -P -n
```

- `-i`: Show network files.
- `-P`: Don't convert port numbers to names.
- `-n`: Don't resolve hostnames.

### Interpreting the Output

- **Local Address**: Shows IP and port (`*:80` means all IPs on port `80`).
- **PID/Program name**: The process ID and the name of the program using the port.

You can use any of these commands to list all ports that are currently in use on your Ubuntu system.

<hr>

To see the status of services on your system, including active, inactive, and failed services, you can use the `systemctl` command with various options:

### 1. Show All Services

To list all services, both active and inactive:

```bash
systemctl list-units --type=service
```

### 2. Show Active Services

To see only the active services:

```bash
systemctl list-units --type=service --state=active
```

### 3. Show Inactive Services

To view the services that are not currently running:

```bash
systemctl list-units --type=service --state=inactive
```

### 4. Show Failed Services

To check which services have failed:

```bash
systemctl list-units --type=service --state=failed
```

### 5. Show All Services with Status Information

To get detailed status information for all services (active, inactive, and failed):

```bash
systemctl --all --type=service
```

### 6. Filter Specific Service Status

If you want to see the status of a specific service, you can use:

```bash
systemctl status <service_name>
```

Replace `<service_name>` with the name of the service you want to check, such as `nginx`, `apache2`, etc. 

### Example

- To check the status of the `ssh` service:

```bash
systemctl status ssh
``` 

### 7. To see only the actively running services

To see only the actively running services (active and running programs) on your system using `systemctl`, you can use the following command:

```bash
systemctl list-units --type=service --state=running
```

This command filters and displays only the services that are currently active and in a running state.

This will give you detailed information about whether the service is active, inactive, or failed, along with logs and other status details.

<hr>

To see all the ports currently in use on your Ubuntu system, you can use the `netstat`, `ss`, or `lsof` commands. Here are different ways to check all busy ports:

### Using `ss` Command

`ss` is a modern replacement for `netstat` and provides detailed information about ports in use.

```bash
sudo ss -tulnp
```

- `-t`: Show TCP ports.
- `-u`: Show UDP ports.
- `-l`: Show only listening ports.
- `-n`: Show numerical addresses instead of resolving hostnames.
- `-p`: Show the process using the port.

### Using `netstat` Command

If `netstat` is installed on your system, you can use it to view all busy ports.

```bash
sudo netstat -tulnp
```

- `-t`: Show TCP ports.
- `-u`: Show UDP ports.
- `-l`: Show only listening ports.
- `-n`: Show numerical addresses.
- `-p`: Show the process using the port.

### Using `lsof` Command

`lsof` lists open files and the ports associated with them.

```bash
sudo lsof -i -P -n
```

- `-i`: Show network files.
- `-P`: Don't convert port numbers to names.
- `-n`: Don't resolve hostnames.

### Interpreting the Output

- **Local Address**: Shows IP and port (`*:80` means all IPs on port `80`).
- **PID/Program name**: The process ID and the name of the program using the port.

You can use any of these commands to list all ports that are currently in use on your Ubuntu system.

<hr>
