
## snapd.apparmor.service

## Systemd
In linux one of the initial linux system (meaning they start with boot up) is the **systemd**. It manages services and processes.
- start services in parallel
- manages system processes(start, stop, restart service)
- Handles logging
- Controls system states (shutdown, reboot, sleep)
 ### Systemd commands
 ```bash
 systemctl start nginx
 systemctl stop nginx
 systemctl status nginx
 #active/death
 systemctl enable ssh
 #ssh will start after startup
 systemctl list-units --type=service 
 #list all services
 # or
 ps aux | grep desired process name
 
 journalctl -xe 
 #logs
 journalctl -u ssh.service --no-pager
 #ssh logs
 ```




### Summary: Service and Process Management in Linux

#### **Understanding Services and Processes**

Services (daemons) in Linux run in the background without direct user interaction. They can be:

- **System Services** – Essential for system operation, like hardware initialization.
- **User-Installed Services** – Additional features, like SSH or web servers.

Daemons are often named with a **"d"** at the end (e.g., `sshd`, `systemd`).

#### **Managing Services with `systemctl`**

1. **Start a service**:
    
    ```bash
    systemctl start ssh
    ```
    
2. **Check service status**:
    
    ```bash
    systemctl status ssh
    ```
    
3. **Enable service on boot**:
    
    ```bash
    systemctl enable ssh
    ```
    
4. **List all active services**:
    
    ```bash
    systemctl list-units --type=service
    ```
    
5. **Check logs for errors**:
    
    ```bash
    journalctl -u ssh.service --no-pager
    ```
    

#### **Managing Processes**

6. **Find a running process**:
    
    ```bash
    ps -aux | grep ssh
    ```
    
7. **Kill a process** (forcefully terminate using its PID):
    
    ```bash
    kill -9 <PID>
    ```
    
8. **View available signals for `kill`**:
    
    ```bash
    kill -l
    ```
    

#### **Background and Foreground Processes**

9. **Suspend a process** (Ctrl + Z):
    
    ```bash
    jobs
    ```
    
10. **Resume in background**:
    
    ```bash
    bg
    ```
    
11. **Resume in foreground**:
    
    ```bash
    fg <jobID>
    ```
    
12. **Run a process in the background**:
    
    ```bash
    ping -c 10 www.hackthebox.eu &
    ```
    

#### **Executing Multiple Commands**

13. **Run commands sequentially (ignores errors)**:
    
    ```bash
    echo '1'; echo '2'; echo '3'
    ```
    
14. **Run commands only if the previous one succeeds**:
    
    ```bash
    command1 && command2
    ```
    
15. **Use pipes to pass output between commands**:
    
    ```bash
    ls | grep "file"
    ```
    

This guide covers essential service and process management tasks in Linux.

```




PID - Process ID
Is what all processes have. 

PPID - Parent Process ID
The process that started it ID.

The `ps aux` command in Linux displays a detailed list of all running processes.

### Breakdown:

- `ps` → Shows process information.
- `a` → Lists processes from all users.
- `u` → Displays user-related details (CPU, memory usage, etc.).
- `x` → Includes processes not attached to a terminal (like daemons).


---
## Examples

```bash
$systemctl start ssh
┌─[yakoti@parrot]─[~]
└──╼ $systemctl status ssh
● ssh.service - OpenBSD Secure Shell server
     Loaded: loaded (/lib/systemd/system/ssh.service; disabled>
     Active: active (running) since Sat 2025-02-08 16:34:02 EE>
       Docs: man:sshd(8)
             man:sshd_config(5)
    Process: 1965 ExecStartPre=/usr/sbin/sshd -t (code=exited,>
   Main PID: 1966 (sshd)
      Tasks: 1 (limit: 4505)
     Memory: 2.7M
        CPU: 29ms
     CGroup: /system.slice/ssh.service
             └─1966 "sshd: /usr/sbin/sshd -D [listener] 0 of 1>
lines 1-12/12 (END)

```

```bash
systemctl start apache2
systemctl status apache2
systemctl kill apache2
#-system control
```

(Apache2 is web server software that acts like a middle man between the browser and the files and data on the server. Handling http request response. allowing you to host websites)


```
python3 -m http.server 8080
```

`python3 -m http.server 8080`, you started a local HTTP server using the Python `http.server` module.

- **`http.server`**: This is a built-in Python module that allows you to quickly start a simple HTTP server.
- **`-m`**: This flag tells Python to run the module as a script.
- **`8080`**: This is the port number on which the server will listen for incoming requests. In this case, you specified port 8080.
see at http://0.0.0.0:8080/


- **Signals**: Used to interact with processes, with common signals including SIGHUP, SIGINT, and SIGTERM.




