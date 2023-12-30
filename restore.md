## Install virtualmin
- Per docs, install first
```
wget https://software.virtualmin.com/gpl/scripts/virtualmin-install.sh
sudo sh virtualmin-install.sh
```

## restore linuxoverview page

## Terminal to root
- promote yourself
```
su -
```

## restore fstab
```
cp /path/to/backup/fstab /etc/fstab
```

## Make downloads faster
```
nano /etc/dnf/dnf.conf
max_parallel_downloads=10
```

## Update all core packages
```
dnf group update core
```

## add flatpak
```
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
flatpak update
```

## enable flathub in discovery
- Open Settings in the Discover App and enable flatplack
```
dnf -y update && sudo dnf -y upgrade --refresh
```

## Reboot
```
reboot
```

## Update hardware
```
fwupdmgr refresh --force 
fwupdmgr get-updates 
fwupdmgr update
```

## Enable intel hardware encoding
```
dnf install intel-media-driver
```

## Disable NetworkManager-wait-online.service
Disabling it can decrease the boot time by at least ~15s-20s:
```
systemctl disable NetworkManager-wait-online.service
```

## Disable Gnome Software from Startup Apps
```
sudo rm /etc/xdg/autostart/org.gnome.Software.desktop -y
```

## Microsoft Fonts
```
sudo dnf install -y curl cabextract xorg-x11-font-utils fontconfig &&
sudo rpm -i https://downloads.sourceforge.net/project/mscorefonts2/rpms/msttcore-fonts-installer-2.6-1.noarch.rpm
```

## set custom name
```
sudo hostnamectl set-hostname "New_Custom_Name"
```

## Firewall Configuration
```
sudo firewall-cmd --add-port=3389/tcp --permanent
sudo firewall-cmd --reload
```

## Load Intel GPU and assign admin rights to everyone
```
sudo modprobe i915 && sudo chmod -R 777 /dev/dri
```
   
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

## Install docker
```
dnf config-manager --add-repo https://download.docker.com/linux/fedora/docker-ce.repo
dnf install docker-ce docker-ce-cli containerd.io
systemctl start docker
```

## restore Plex
- create your folder under your home folder
- then run this cmd to symbolic
```
ln -s /home/iamgroot/webengine/ /webengine
```

- its wise to add your items under the drive you created earlier
- this ensures all furture files and folders are owned by you
