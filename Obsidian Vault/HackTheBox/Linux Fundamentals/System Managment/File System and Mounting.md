

---

### **File System Management in Linux**

Linux supports various file systems:

- **ext2**: No journaling, low overhead (USB drives).
- **ext3/ext4**: Journaling, ext4 is the modern default for performance and reliability.
- **Btrfs**: Advanced features like snapshotting and data integrity checks.
- **XFS**: High performance for large files.
- **NTFS**: For compatibility with Windows systems.

**Inodes**: Data structures that store file metadata (permissions, size, timestamps) but not the file data. They function like library index cards, helping the OS manage files.

### **File Types in Linux**

1. **Regular Files**: Text, binary, or executables.
2. **Directories**: Containers for other files.
3. **Symbolic Links (Symlinks)**: Shortcuts to other files or directories.

---

### **Disk Management**

- **`fdisk`**: A tool for partitioning drives and viewing partition tables.  
    Example:
    
    ```bash
    sudo fdisk -l
    ```
    
    Output shows disk size, partition type, and details.
    
- **Partitions**: Can be formatted with various file systems (e.g., ext4, NTFS) and mounted separately.
    

### **Mounting and Unmounting**

- **Mounting**: Assigns a file system to a directory (mount point).
    
    ```bash
    sudo mount /dev/sdb1 /mnt/usb
    cd /mnt/usb && ls -l
    ```
    
- **Unmounting**: Detaches the file system from the mount point.
    
    ```bash
    sudo umount /mnt/usb
    ```
    
- **`/etc/fstab`**: A file listing file systems for automatic mounting at boot. Example entry:
    
    ```txt
    /dev/sda1 / ext4 defaults 0 0
    ```
    
- **List all mounted drives**:
    
    ```bash
    mount
    ```
    
- **View files in use** (if a file system is busy):
    
    ```bash
    lsof | grep username
    ```
    

Adding `noauto` to `/etc/fstab` ensures a partition is not auto-mounted at boot.

---

This overview covers key concepts of file system management, disk handling, and mounting commands in Linux.