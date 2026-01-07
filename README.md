# Linux File System Hierarchy (FHS)

Linux follows the **Filesystem Hierarchy Standard (FHS)**, which defines how directories are structured and what purpose each directory serves.  
Everything in Linux starts from the **root directory `/`**.

1) / :- Root Directory
- The top-level directory of Linux
- All other directories exist under `/`
- Only the root (admin) user can modify critical files

2) /bin :- Binary Files (User Commands)
- Essential command binaries required for system operation
- Available for all users
**Examples**
- ls
- cp
- mv
- rm
- cat

3) /sbin :- System Binaries
- System-level commands used by the administrator
- Mostly for system maintenance
**Examples**
- shutdown
- reboot
- ifconfig
- fsck

4) /etc :- Configuration Files
- Stores system-wide configuration files
- No binaries, only text configuration files
**Important Files**
- passwd → user accounts
- shadow → encrypted passwords
- group → group info
- hosts → hostname mapping
- ssh/sshd_config → SSH settings
**Security Note**
Misconfigured `/etc` files can lead to privilege escalation.

5) /home :- User Home Directories
- Each normal user gets a directory here
- Stores personal files, documents, downloads

4)/root :- Root User Home
- Home directory of the root user
- Separate from `/home`
  
 5) /var :- Variable Data
- Frequently changing files
**Contains**
- Logs → `/var/log`
- Mail → `/var/mail`
- Spool files → `/var/spool`
**Security Importance**
Log files are crucial for SOC and incident investigation.

6) /usr :- User System Resources
- Installed software, libraries, documentation
- Largest directory on many systems
**Subdirectories**
- /usr/bin → user commands
- /usr/sbin → admin commands
- /usr/lib → libraries
- /usr/share → shared data

7) /lib and /lib64 :- Shared Libraries
- Libraries required by binaries in `/bin` and `/sbin`
- Kernel modules stored in `/lib/modules`

8) /tmp :- Temporary Files
- Temporary files created by applications
- Files are often deleted on reboot
**Security Note**
Attackers may hide malicious scripts here.

9) /dev :- Device Files
- Represents hardware devices as files
**Examples**
- sda → hard disk
- tty → terminal
- null → discard output

10) /proc :- Process Information (Virtual Filesystem)
- Provides information about running processes
- Generated in memory, not stored on disk
**Examples**
- cpuinfo → CPU details
- meminfo → memory usage
- uptime → system uptime

11) /sys :- System Information
- Interface to kernel and hardware
- Used for device and driver management

12) /boot :- Boot Loader Files
- Files needed to boot the system
**Contains**
- Kernel (vmlinuz)
- initramfs
- GRUB configuration

13) /mnt :- Temporary Mount Point
- Used to mount filesystems temporarily
  
14) /media :- Removable Media
- Auto-mounted devices
**Examples**
- USB drives
- CD/DVD

15) /opt :- Optional Software
- Third-party or commercial software
- Keeps additional software isolated

16) /srv :-Service Data
- Data served by services like web or FTP servers

17) /run :- Runtime Data
- Stores temporary runtime data
- Cleared on reboot

