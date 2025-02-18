```bash

ifconfig
ip addr

ifconfig.me
#write in the browser


ifconfig ens33 up/down
ifconfig set netmask 255.255.255.0
#set the netmask 
ifconfig ens33 192.168.213.99
#set my ip address at network level to 99. 
#if you change some of the netmask number you will disconnect or swich to other network.
netstat -avp | grep LISTEN
#list the listening ports on your system
netstat -tupn | grep ESTABLISHED
#it returns ip:port and firefox ip:443 for example
#so they communicate through this doors.
```

---
Let me break down the most practical and immediately useful knowledge from this article, focusing on what will help you in real-world scenarios.

1. Network Troubleshooting Tools You Should Know:
The most important tools for diagnosing network issues are:

PING - Your First Diagnostic Tool
```bash
ping google.com
```
This is like knocking on a door to see if anyone's home. If you can't reach a website or server, ping it first. If ping fails, you know there's a connection problem. If it works, the issue is probably with the specific service you're trying to use.

TRACEROUTE - Finding Where Connection Problems Are
```bash
traceroute google.com
```
Think of this as looking at a roadmap of how your data travels. If a website is slow or unreachable, traceroute shows you where the problem might be. For example, if all routes stop at your router, you know the problem is in your local network.

2. Common Network Issues and Their Quick Fixes:
When something's not working, check these in order:
- Is your physical connection okay? (Check cables)
- Can you ping your router? (Usually 192.168.1.1)
- Can you ping 8.8.8.8? (Google's DNS - if this works but website names don't, it's a DNS issue)
- Did you check your DNS settings in /etc/resolv.conf?

1. Basic Security Concepts:
Think of these three main security approaches like different types of security guards:

- DAC (Discretionary Access Control): Like having a building where each room owner decides who gets a key
- MAC (Mandatory Access Control): Like military clearance levels - no matter who you are, you need the right security level
- RBAC (Role-Based Access Control): Like a hospital where access depends on your job (doctor, nurse, admin)

2. Quick Network Health Check:
When you join a new network or something's not working, run these commands in order:
```bash
# Check if you have an IP address
ip addr show

# Check if you can reach your gateway
ping $(ip route | grep default | awk '{print $3}')

# Check if you can reach the internet
ping 8.8.8.8

# Check if DNS is working
ping google.com
```

3. Remember DNS is Often the Culprit:
If you can ping an IP address but not a website name, it's probably DNS. Quick fix:
```bash
# Add Google's DNS servers
sudo nano /etc/resolv.conf
# Add these lines:
nameserver 8.8.8.8
nameserver 8.8.4.4
```

The most important thing to remember is the order of troubleshooting:
4. Can you reach your local network? (ping router)
5. Can you reach the internet? (ping 8.8.8.8)
6. Can you resolve domain names? (ping google.com)
7. Is the specific service/port you need working? (try connecting to the service)

This systematic approach will help you solve about 80% of common network issues you'll encounter. Would you like me to elaborate on any of these points or provide more specific examples?

