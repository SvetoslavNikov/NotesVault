[[Linux Fundamentals]]

| **Command** | **Description**                                                                                                                    |
| ----------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| dpkg -l     | dpkg - manages debian packages -l list all of them                                                                                 |
| `whoami`    | Displays current username.                                                                                                         |
| `id`        | Returns users identity                                                                                                             |
| `hostname`. | Sets or prints the name of current host system.                                                                                    |
| `uname`     | (Unix name) Prints basic information about the operating system name and system hardware.                                          |
| `pwd`       | print working directory                                                                                                            |
| `ifconfig`. | The ifconfig utility is used to assign or to view an address to a network interface and/or configure network interface parameters. |
| `ip`        | Ip is a utility to show or manipulate routing, network devices, interfaces and tunnels.                                            |
| `netstat`   | (Network Statistics) Shows network status.                                                                                         |
| `ss`        | (Socket Statistics) Another utility to investigate sockets.                                                                        |
| `ps`        | (Process Status) Shows process status.                                                                                             |
| `who`       | (Who is logged in) Displays who is logged in.                                                                                      |
| `env`       | (Environment) Prints environment or sets and executes command.                                                                     |
| `lsblk`     | List Block Devices.                                                                                                                |
| `lsusb`     | List USB Devices.                                                                                                                  |
| `lsof`      | List Open Files.                                                                                                                   |
| `lspci`     | List PCI Devices.                                                                                                                  |
| &&          | two command same line (cd home && clear)                                                                                           |




. - not installed in arch
### Logging In via SSH

`Secure Shell` (`SSH`) - protocol that allows clients to access and execute commands or actions on remote computers

*Permanently installed standard tool* on Linux-based host, servers or Unix-like OS

We can connect to our targets with the following command:

```shell-session
yakoti@htb[/htb]$ ssh htb-student@[IP address]
```



# exercise


I'll help you find all this system information step by step. Let's assume you're already connected via SSH to the target system using the previously provided credentials.

To find the path to htb-student's mail:
```bash
echo /var/mail/htb-student
# or we can check /etc/passwd
grep htb-student /etc/passwd
```
The mail directory for Linux users is typically located at /var/mail/[username].

To find htb-student's shell:
```bash
grep htb-student /etc/passwd
```
This command will show us a line containing all the user's information, including their default shell which is listed as the last field after the last colon (:).

To check the kernel release:
```bash
uname -r
```
The `uname` command with the `-r` flag specifically shows the kernel release version.

To find the network interface with MTU 1500:
```bash
ip link show
# or alternatively
ifconfig
```
This will show all network interfaces and their MTU settings. Look for the interface that shows "mtu 1500" in its configuration.

Let me explain what each of these commands does:

- `/var/mail/` is a standard directory in Linux systems where user mailboxes are stored. Each user typically has their own mail file named after their username.

- `/etc/passwd` is a system file that contains essential information about all user accounts. Each line represents one user and contains fields separated by colons (:). The last field specifies the user's default shell.

- `uname -r` shows the kernel release version. The kernel is the core of the operating system, and its version number tells us which features and security updates are installed.

- `ip link show` displays network interface information. MTU (Maximum Transmission Unit) is the largest size of data packet that can be transmitted through that interface. 1500 bytes is a common standard MTU size for Ethernet networks.

Would you like me to explain any of these concepts in more detail?
