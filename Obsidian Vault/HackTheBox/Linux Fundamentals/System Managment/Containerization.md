## Security
Containers are separated from other containers and the host. So malicious activities affecting the host or other containers does not spread. But it is not prone like actual VM to: 
- **Privilege Escalation:**  
    This occurs when an attacker exploits a bug or misconfiguration in software to gain higher-level permissions than they should have, such as moving from a limited user account to root. This type of vulnerability is usually related to software bugs or configuration issues rather than how data is stored or encrypted on disk.
    
- **Container Escapes:**  
    Container escapes refer to a scenario where a process running inside a container manages to break out and access the host system. This is generally a flaw or misconfiguration in the containerization technology itself, and isn’t directly affected by disk encryption or partitioning schemes.


1. allows to use right tool for the job - micro services architecture, like
- go for catalog, legacy system, java script frontend,
- great for agile , CI - Continues Integration,
- individual component scale and tackling issues
lightweight standardized ways to run code

Container image - instruction to build a container
we have the os, the commands to install packages and dependencies, the code, the commands to run it, the ports for i/o
























