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

Linux is the alternative to Microsoft turning into Nolan Sorrento
"Once we can roll back some of Halliday's ad restrictions, we estimate we can sell up to 80% of an individual's visual field before inducing seizures, so picture this..."

This guide will walk you thorough understanding of Linux basics and essential skills for system management.

### 2. Linux File Structure

Linux uses a hierarchical directory structure that starts from the root directory, '/'. Instead of 'C:\', the base is '/' and for something like 'C:\Users\You\Desktop', it's '/home/you/Desktop'. Here’s a quick rundown of some directories:

- **`/` (Root)**: The base of the file system. Everything branches from here.
- **`/bin`**: Contains essential user binaries or programs, vital for booting and running the system.
- **`/boot`**: Holds the Linux kernel, initial RAM disk image, and boot loader – crucial for starting the system.
- **`/dev`**: This is where device files live. Linux treats devices like files, which are interfaces to drivers.
- **`/etc`**: System-wide configuration files and scripts are stored here, integral for startup and overall system behavior.
- **`/home`**: Home directories for users. Personal files and settings go here, similar to 'C:\\Users' in Windows.
- **`/lib`**: Houses shared library images needed by system binaries.
- **`/media`** and **`/mnt`**: Used for mounting external devices and filesystems, like USB drives.
- **`/opt`**: A spot for optional or third-party software.
- **`/sbin`**: System administration binaries – more specialized than `/bin`.
- **`/usr`**: A large directory containing most user applications and utilities, with subdirectories for binaries, system libraries, documentation, and more.
- **`/var`**: Variable data—logs, mail, spool files, and other dynamic files.
