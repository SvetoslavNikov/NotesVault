The `/etc/passwd` file in Linux contains user account information. Each line represents a user and has **7 fields** separated by colons (`:`).

### **Typical Format:**

```
username:x:UID:GID:full_name:home_directory:shell
```

### **Fields Explained:**

1. **Username** – The login name (`root`, `user1`, etc.).
2. **Password Placeholder (`x`)** – Password is stored in `/etc/shadow` instead.
3. **User ID (UID)** – A unique number for the user (`0` for root, `1000+` for normal users).
4. **Group ID (GID)** – The user's primary group ID.
5. **Full Name (or Comment Field)** – Optional description.
6. **Home Directory** – The user's home folder (e.g., `/home/user1`).
7. **Shell** – The default shell (`/bin/bash`, `/bin/zsh`, `/usr/sbin/nologin`, etc.).

### **Example Entries:**

```
root:x:0:0:root:/root:/bin/bash
user1:x:1001:1001:John Doe:/home/user1:/bin/zsh
nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin
```

- **Root user** has UID `0` and uses `/bin/bash`.
- **Regular user (`user1`)** has UID `1001` and uses `/bin/zsh`.
- **System account (`nobody`)** has `/usr/sbin/nologin` (cannot log in).

This file is essential for user management in Linux.