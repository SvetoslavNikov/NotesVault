![[Pasted image 20250128142824.png]]

[[Linux Fundamentals]]

## Linux Filesystem Structure

The whole file system evolved by consensus over eons and is usually consistent from one distro to another. The burden is also on developers writing install applications to use this file system and not make up weird folder schemes on their own. As for users, they have complete freedom to do whatever they want in their own directory.

## /bin

Where binary programs live.

## /boot

The special programs that start the system when you turn the machine on.

## /dev

All the "device" listings for hardware of every conceivable flavor, along with some "imaginary" devices like `/dev/null` and `/dev/zero`. When you get a random number, it usually comes from `/dev/random`.

## /etc

Configuration files.

## /home

User directories live here.

## /lib

The library files that programs need to run if they are compiled to link against these libraries.

## /lost+found

Look here after a system crash, kernel panic, or other extreme scenarios to find "orphaned" files.

## /misc

Kind of reminds you of `/etc`, doesn't it? Every time I see this folder on a system, it's empty, but I ascertain that it stands for "miscellaneous," and I think it may be a place for users to keep their own `/etc` type files.

## /mnt

"Mount"—the directory that acts as a gateway to every other disk or file system. Floppies are accessed from `/mnt/floppy`, your second hard drive might be `/mnt/hd`, and so on.

## /opt

"Optional"—where programs installed after the initial system install sometimes end up.

## /proc

Running "processes". The "everything is a file" paradigm carried to the Linux degree! This folder hosts files that keep tabs on things like what daemons are running and the process ID of Emacs while you have Emacs open.

## /root

Root's home directory.

## /sbin

The "system-administrator's bin file," which hosts programs that would be in `/bin` if they didn't have "root-only" access permissions.

## /tmp

"Temporary" files, used by programs that need to throw together a data file on-the-fly in preparation for executing some other task. This folder gets flushed on reboot.

## /usr

"User"—practically a whole other system in here.

- `/usr/bin`: More binaries.
- `/usr/doc` and `/usr/share/doc`: Documentation folders.
- `/usr/share/games/fortune`: Where the funny quotes come from when you log on (if that feature is enabled).
- `/usr/share/wallpapers`: Where desktop backgrounds are stored.
- `/usr/local/bin`: Where newly installed programs sometimes end up.

## /var

"Variable"—system logs live here, recording such things as the last commands typed at the prompt, start-up boot messages, and more.

The whole file system evolved by consensus over eons and is usually consistent from one distro to another. The burden is also on developers writing install applications to use this file system and not make up weird folder schemes on their own. As for users, they have complete freedom to do whatever they want in their own directory.
  
