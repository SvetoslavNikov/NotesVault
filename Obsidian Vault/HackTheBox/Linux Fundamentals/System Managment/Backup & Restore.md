Here’s a well-formatted version of your instructions:

---

## 1. Create a script to archive a folder on the backup server

```bash
vim RSYNC_Backup.sh
chmod a+x RSYNC_Backup.sh
```

Add the following content to `RSYNC_Backup.sh`:

```bash
#!/bin/bash

# Add logging to help troubleshoot any issues
exec 1> >(logger -s -t $(basename $0)) 2>&1

# Use a specific SSH key for this backup
rsync -avz -e "ssh -i /home/yakoti/.ssh/backup_key" \
    /home/yakoti/server \  # Folder to be backed up
    htb-student@10.129.171.53:~/backup  # Backup location on the target server

# rsync options:
# -a: Archive mode
# -v: Verbose log
# -z: Compress data
# -e encrypted
```

---

## 2. Add the script to `crontab`

Open `crontab` for editing:

```bash
crontab -e
```

Add the following line to run the backup every minute:

```bash
* * * * * /home/yakoti/RSYNC_Backup.sh
```

Logs for the executed `crontab` can be found in `/var/mail/yakoti`.

---

## 3. Create an SSH key for automatic connection without a password

```bash
ssh-keygen -t ed25519 -f ~/.ssh/backup_key
```

This command will generate two files:

- `backup_key`: Private key
- `backup_key.pub`: Public key

---

## 4. Copy `backup_key.pub` to the target system

Copy the contents of `backup_key.pub` to the `.ssh/authorized_keys` file on the backup server to allow no password SSH access.



---


### Possible Missing or Additional Steps:

1. **Permissions for SSH key**: After creating the SSH key pair (`backup_key` and `backup_key.pub`), ensure that the permissions are set correctly. This can prevent SSH from refusing the key due to security issues.
    
    On your local system, set the correct permissions for the private key:
    
    ```bash
    chmod 600 ~/.ssh/backup_key
    ```
    
    On the target server, set the correct permissions for the `authorized_keys` file:
    
    ```bash
    chmod 700 ~/.ssh
    chmod 600 ~/.ssh/authorized_keys
    ```
    
2. **Testing the SSH connection**: Before automating the backup with `rsync` or `cron`, it's a good idea to test the SSH connection to make sure it's working without a password prompt:
    
    ```bash
    ssh -i ~/.ssh/backup_key htb-student@10.129.171.53
    ```
    
    If you can log in without a password, then the SSH key setup is working.
    
3. **Ensure rsync is installed**: Make sure `rsync` is installed on both the local and remote systems:
    
    ```bash
    sudo apt install rsync   # On Debian/Ubuntu systems
    sudo yum install rsync   # On CentOS/RHEL systems
    ```
    
4. **Check logs after running the script**: You’re using `logger` to log messages. You can check the logs by running:
    
    ```bash
    tail -f /var/log/syslog  # On most systems
    ```
    
    or
    
    ```bash
    tail -f /var/log/messages  # For some distributions
    ```
    

### Full Description of `rsync` Options:

Now, let’s dive into the full explanation of the options you're using in the `rsync` command.

#### `rsync` Command Breakdown:

```bash
rsync -avz -e "ssh -i /home/yakoti/.ssh/backup_key" /home/yakoti/server htb-student@10.129.171.53:~/backup
```

#### `-a` (Archive mode):

- This option tells `rsync` to operate in archive mode, which means it will copy the files recursively and preserve important attributes like:
    - **Permissions**
    - **Timestamps**
    - **Symbolic links**
    - **Owner and group**
    - **Special files** (such as device files)
- Essentially, it ensures the copied files are as identical as possible to the source, making the backup an exact replica.

#### `-v` (Verbose mode):

- The `-v` option enables verbose output, which means `rsync` will show a list of the files being transferred along with additional information, such as progress or any errors. This is helpful for debugging and understanding what’s being copied.

#### `-z` (Compression):

- The `-z` option enables compression, which helps reduce the amount of data transferred over the network by compressing files during the transfer. This is particularly useful if you are backing up large files over a slow network connection.

#### `-e "ssh -i /home/yakoti/.ssh/backup_key"` (Using SSH with a specific key):

- The `-e` option allows you to specify the remote shell program to use (by default, it uses `ssh`).
    
- In this case, you are explicitly telling `rsync` to use the SSH protocol with a specific private key (`backup_key`) to authenticate the connection.
    
    `-e "ssh -i /home/yakoti/.ssh/backup_key"` tells `rsync` to use the SSH key located at `/home/yakoti/.ssh/backup_key` for authentication, ensuring that the transfer is secure and passwordless.
    

### Full Breakdown of Other Commands:

1. **`exec 1> >(logger -s -t $(basename $0)) 2>&1`**:
    
    - This line redirects the output and errors of the script to the system log. It's useful for debugging and tracking the script's activity in real-time.
    - `1>` redirects standard output (stdout), and `2>&1` redirects standard error (stderr) to the same location.
    - `logger -s -t $(basename $0)` sends the output to the syslog with a tag corresponding to the script's name, making it easy to filter logs related to this backup script.
2. **`ssh-keygen -t ed25519 -f ~/.ssh/backup_key`**:
    
    - This generates a new SSH key pair using the `ed25519` algorithm (a more secure and modern choice compared to RSA).
    - `-f ~/.ssh/backup_key` specifies the path and filename for the key. The private key is saved as `backup_key`, and the public key is saved as `backup_key.pub`.
3. **`crontab -e`**:
    
    - This command opens the crontab configuration for editing, allowing you to add scheduled tasks (cron jobs).
    - The line `* * * * * /home/yakoti/RSYNC_Backup.sh` tells `cron` to run the backup script every minute.

---

### Conclusion:

Everything looks correct in your original steps, but just be mindful of SSH key permissions and testing the SSH connection before automation. The descriptions of the commands should give you a clear understanding of what each part does.

Let me know if you need any further clarification or run into issues!