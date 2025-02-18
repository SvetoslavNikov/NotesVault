packet managers

dpkg - works lower level with .deb files when they end needing more dependencies we have to manually install them .

apt - advanced package tool - used for higher level package management, it has dependency resolution - meaning automatically install the necessary dependencies.

pip - for python

git - for version control


## APT Cache
Used to store information about packages stored on our system.

Examples
```
sudo dpkg -i (for install) strace.deb 
```

*strace is a diagnostic, debugging and instructional userspace utility for Linux. It is used to monitor and tamper with interactions between processes and the Linux kernel, which include system calls, signal deliveries, and changes of process state.*

```
mkdir newdir && git clone https://....
```
**evil-winrm**
some shell for hacking more info here: https://github.com/Hackplayers/evil-winrm
