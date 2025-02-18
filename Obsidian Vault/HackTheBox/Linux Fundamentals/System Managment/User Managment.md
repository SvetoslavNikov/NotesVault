Users are stored in the passwd file
```bash
(echo "Username   Password   UID   GID   Full_Name       Home_Directory        Shell"; cat /etc/passwd 2>/dev/null | grep -v nologin | grep -v false | tr ":" " ") | column -t

cut -d: -f1 /etc/passwd
#just the names 
```

The `/etc/shadow` file is a critical system file that stores encrypted password information for all user accounts. For security reasons, it is readable and writable only by the root user to prevent unauthorized access to sensitive authentication data.

---

| **Command** | **Description**                                                                                                                                            |
| ----------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `sudo`      | Execute command as a different user.                                                                                                                       |
| `su`        | The `su` utility requests appropriate user credentials via PAM and switches to that user ID (the default user is the superuser). A shell is then executed. |
| `useradd`   | Creates a new user or update default new user information.                                                                                                 |
| `userdel`   | Deletes a user account and related files.                                                                                                                  |
| `usermod`   | Modifies a user account.                                                                                                                                   |
| `addgroup`  | Adds a group to the system.                                                                                                                                |
| `delgroup`  | Removes a group from the system.                                                                                                                           |
| `passwd`    | Changes user password.                                                                                                                                     |