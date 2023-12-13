# /windowstolinux guide

1. Introduction
2. Linux File Structure
3. Basic Linux Commands
4. Windows vs. Linux
5. Initial Fedora Setup
6. Software Installation
7. Firewall Configuration
8. Directory Creation and Permissions
9. Additional System Configurations
10. Docker Compose Configuration
11. Customizing Your Linux Environment
12. Conclusion

### 1. Introduction

Linux is the alternative to Microsoft turning into Nolan Sorrento. "Once we can roll back some of Halliday's ad restrictions, we estimate we can sell up to 80% of an individual's visual field before inducing seizures, so picture this..." 

This guide will walk you through understanding Linux basics and essential skills for system management.

### 2. Linux File Structure

Linux uses a hierarchical directory structure that starts from the root directory, '/'. This replaces the 'C:' in Windows, meaning the base is '/' and paths like 'C:\\Users\\You\\Desktop' in Linux are '/home/you/Desktop'. Below is an overview of some key directories:

- **`/ (Root)`**: The foundational level. All directories and files stem from here.
- **`/bin`**: Houses essential user programs necessary for system operations.
- **`/boot`**: Contains the Linux kernel and boot loader, crucial for system startup.
- **`/dev`**: Device files representing hardware components.
- **`/etc`**: System-wide configuration files and scripts.
- **`/home`**: User personal directories, like 'C:\\Users' in Windows.
- **`/lib`**: Shared libraries and kernel modules.
- **`/media`** and **`/mnt`**: Mounting points for external devices and filesystems.
- **`/opt`**: Optional or third-party software.
- **`/sbin`**: System administration binaries.
- **`/usr`**: A broad directory for most user-level applications and utilities.
- **`/var`**: Variable data like logs, mail, and spool files.

To visualize this, here's a simplified representation of the Linux directory structure:

/
├── bin
├── boot
├── dev
├── etc
├── home
│   └── you
│       └── Desktop
├── lib
├── media
├── mnt
├── opt
├── sbin
├── usr
└── var
