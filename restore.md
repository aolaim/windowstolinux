## Install virtualmin
wget https://software.virtualmin.com/gpl/scripts/virtualmin-install.sh
sudo sh virtualmin-install.sh

## Make downloads faster
sudo nano /etc/dnf/dnf.conf
max_parallel_downloads=10

## Install docker
sudo dnf config-manager --add-repo https://download.docker.com/linux/fedora/docker-ce.repo
sudo dnf install docker-ce docker-ce-cli containerd.io
sudo systemctl start docker

## Update all core packages
sudo dnf group update core

## add flatpak
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
flatpak update

## enable flathub in discovery
- we will install apps from here if possible

sudo dnf -y update && sudo dnf -y upgrade --refresh

#reboot

sudo fwupdmgr refresh --force 
sudo fwupdmgr get-updates 
sudo fwupdmgr update

#Enable hardware encoding
sudo dnf install intel-media-driver

#Disable NetworkManager-wait-online.service
#Disabling it can decrease the boot time by at least ~15s-20s:
sudo systemctl disable NetworkManager-wait-online.service

#Disable Gnome Software from Startup Apps
sudo rm /etc/xdg/autostart/org.gnome.Software.desktop

#Microsoft Fonts
sudo dnf install -y curl cabextract xorg-x11-font-utils fontconfig
sudo rpm -i https://downloads.sourceforge.net/project/mscorefonts2/rpms/msttcore-fonts-installer-2.6-1.noarch.rpm

#restore linuxoverview page 
#restore fstab

#set custom name
sudo hostnamectl set-hostname "New_Custom_Name"

7. **Firewall Configuration**
   - `sudo firewall-cmd --add-port=3389/tcp --permanent`
   - `sudo firewall-cmd --add-service=cockpit --permanent`
   - `sudo firewall-cmd --reload`
   
   8. **Directory Creation and Permissions**
   - `cd /`
   - `sudo mkdir yourfolder`
   - `sudo chown -R $(whoami):$(id -gn $(whoami)) yourfolder`
   - mount your shares to a central location 

   sudo modprobe i915 && sudo chmod -R 777 /dev/dri
   
#Software to install
#flatpak install flathub com.usebottles.bottles
#flatpak install flathub org.remmina.Remmina
#1password
#cpux
#gparted
#gtekstresstesting
#Kstars
#timeshift
#neofetch
#
#
#
#
#
#
#
#
#
#
#
#
#
#
#
#
#
#
#
#
#
