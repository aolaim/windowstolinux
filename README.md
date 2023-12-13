#/windowstolinux

## Linux File Structure
- **`/mnt`**: Used for mounted file systems or shared drives.
- **`/opt`**: Directory for third-party software applications.
- **`/var`**: Contains variable data like logs, databases, etc.
- **`/usr`**: Stores user binaries, documentation, libraries, header files.

## Basic Linux Commands
- **`cd /`**: Navigates to the root directory (equivalent to `C:\` in Windows).
- **`cd ..`**: Moves up one directory level.
- **`ll`**: Lists files and directories with detailed information (similar to `ls -l`).

## Initial Fedora Setup
1. **Update Package Manager and Repositories**
2. **Software Installation**
3. **Firewall Configuration**
4. **Directory Creation and Permissions**
5. **Additional System Configurations**
   - `sudo dnf update -y && sudo dnf upgrade --refresh -y`
   - `sudo dnf install https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm`
   - `sudo dnf install https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm`

6. **Software Installation**
   - `sudo dnf install xrdp neofetch qemu @Virtualization ffmpeg --allowerasing python3-pip baobab timeshift dnfdragora cockpit`
   - `pip3 install youtube-dl`

7. **Firewall Configuration**
   - `sudo firewall-cmd --add-port=3389/tcp --permanent`
   - `sudo firewall-cmd --add-service=cockpit --permanent`
   - `sudo firewall-cmd --reload`

8. **Directory Creation and Permissions**
   - `cd /`
   - `sudo mkdir yourfolder`
   - `sudo chown -R $(whoami):$(id -gn $(whoami)) yourfolder`

9. **Additional System Configurations**
   - Mount `/dev/shm` with increased size:
     - `sudo mount -o remount,size=8G /dev/shm`
   - Enable and start services:
     - `sudo systemctl enable xrdp && sudo systemctl start xrdp`
     - `sudo systemctl enable --now cockpit.socket`
   - System sleep and hardware configurations:
     - `sudo systemctl mask sleep.target suspend.target hibernate.target hybrid-sleep.target`
     - `sudo modprobe i915 && sudo chmod -R 777 /dev/dri`
   - Backup and edit fstab file:
     - `sudo cp /etc/fstab /etc/fstab.backup`
     - `sudo blkid # Get UUIDs`
     - `sudo gedit /etc/fstab # Edit with noted UUIDs`
