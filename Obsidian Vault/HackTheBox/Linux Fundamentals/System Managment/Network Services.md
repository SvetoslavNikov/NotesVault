[[LOCALHOST]]
### Summary: Linux Network Services

#### **Importance of Network Services**

- Enable remote operations, file transfers, and network communication
- Identify vulnerabilities during penetration testing
- Misconfigured services can expose sensitive data (e.g., unencrypted FTP)

---

### **1. SSH (Secure Shell)**

- Secure protocol for remote system access and file transfer
- OpenSSH: Most common SSH server
- **Install SSH**:  
    `sudo apt install openssh-server -y`
- **Check server status**:  
    `systemctl status ssh`
- **Login via SSH**:  
    `ssh user@remote_host_ip`
- **Config File**: `/etc/ssh/sshd_config`
- Supports tunneling, port forwarding, and encrypted data transfer

---

### **2. NFS (Network File System)**

- Share files across networks as if stored locally
- Common NFS servers: NFS-UTILS (Ubuntu), OpenNFS (Redhat)
- **Install NFS**:  
    `sudo apt install nfs-kernel-server -y`
- **Check server status**:  
    `systemctl status nfs-kernel-server`
- **Configure NFS**: `/etc/exports`  
    Example:  
    `/path/to/share hostname(rw,sync,no_root_squash)`
- **Mount NFS Share**:  
    `mount remote:/path/to/share local_mount_point`

---

### **3. Web Servers**

- Serve web pages and files over the internet using HTTP/HTTPS
- Apache: Popular web server
- **Install Apache**:  
    `sudo apt install apache2 -y`
- **Config File**: `/etc/apache2/apache2.conf`
    - Options: Indexes, FollowSymLinks
- **Python Web Server** (for single-folder hosting):
    - Install: `sudo apt install python3 -y`
    - Start server: `python3 -m http.server`
    -

---

### **4. VPN (Virtual Private Network)**

- Securely connect to internal networks through encrypted tunnels
- Common VPNs: OpenVPN, L2TP/IPsec, PPTP, SSTP
- OpenVPN: Popular, open-source VPN solution
- Enables secure remote access and traffic anonymization