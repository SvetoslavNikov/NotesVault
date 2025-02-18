[[Linux Fundamentals]]

| cd -           | Jump to the last directory we were in |     |
| -------------- | ------------------------------------- | --- |
| ls -la         | list all in a detailed format         |     |
| cd ..          | parent dir                            |     |
| cd /           | root                                  |     |
| ls -i filename | shows the inode of a file             |     |
|                |                                       |     |

```shell-session
cry0l1t3@htb[~]$ ls -la

total 403188
drwxr-xr-x 2 cry0l1t3 htbacademy 4096 Nov 13 17:37 .bash_history
drwxr-xr-x 2 cry0l1t3 htbacademy 4096 Nov 13 17:37 .bashrc
...SNIP...
drwxr-xr-x 2 cry0l1t3 htbacademy 4096 Nov 13 17:37 Desktop
drwxr-xr-x 2 cry0l1t3 htbacademy 4096 Nov 13 17:34 Documents
drwxr-xr-x 3 cry0l1t3 htbacademy 4096 Nov 15 03:26 Downloads
```


| **Column Content** | **Description**                                                                  |
| ------------------ | -------------------------------------------------------------------------------- |
| `drwxr-xr-x`       | Type and permissions                                                             |
| `2`                | Number of hard links to the file/directory                                       |
| `cry0l1t3`         | Owner of the file/directory                                                      |
| `htbacademy`       | Group owner of the file/directory                                                |
| `4096`             | Size of the file or the number of blocks used to store the directory information |
| `Nov 13 17:37`     | Date and time                                                                    |
| `Desktop`          | Directory name                                                                   |
Some files a hidden (starting with '.'), because they are important configuration files that is important to don't get changed by mistake

## INODE

- Every file on a Linux system has an **inode** (short for **index node**).
- The inode stores **metadata** about the file (size, permissions, owner, timestamps, etc.), but **not** the file name.
- The file name is just a label pointing to the inode.