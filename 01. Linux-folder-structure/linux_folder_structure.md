# 📂 Linux Folder Structure

In Linux, everything starts from the root directory `/`.  
It looks like an upside-down tree 🌳 where `/` is the root and other directories branch out.

---

## 🗂️ Common Directories

| Directory | Purpose |
|-----------|---------|
| `/`       | Root directory (starting point of the file system) |
| `/home`   | Personal folders for users (e.g., `/home/imran`) |
| `/root`   | Home folder for the **root (admin)** user |
| `/bin`    | Essential **binary programs** (like `ls`, `cat`, `cp`) |
| `/sbin`   | System binaries (commands for root/admin) |
| `/etc`    | Configuration files (system-wide settings) |
| `/var`    | Variable data (logs, cache, spool files) |
| `/usr`    | User programs, libraries, documentation |
| `/lib`    | Shared libraries needed for programs in `/bin` and `/sbin` |
| `/tmp`    | Temporary files (cleared on reboot) |
| `/dev`    | Device files (represent hardware like disks, USBs) |
| `/mnt`    | Mount point for temporary devices |
| `/media`  | Mount point for external drives (USB, CD/DVD) |
| `/proc`   | Virtual filesystem with process and kernel info |
| `/boot`   | Boot loader files and Linux kernel |
| `/opt`    | Optional software packages |
| `/srv`    | Data for services (like web servers, FTP servers) |

---

## 🔑 Key Points to Remember
- Linux does **not** use drive letters like Windows (`C:`, `D:`). Everything is inside `/`.
- `/home` is like your “Documents” folder in Windows.
- `/etc` holds settings (like a “Control Panel” in file form).
- `/bin` and `/sbin` contain the commands you use every day.
- `/var/log` contains logs — useful for troubleshooting.

---

## 📌 Example: Navigating the File System
```bash
cd /           # go to root
ls             # list folders
cd /home       # go to user folders
cd /etc        # check configuration files
