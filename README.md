# /windowstolinux
- **Windows VS Linux**
- **Linux File Structure**
- **Software Installation**
- **Firewall Configuration**
- **Directory Creation and Permissions**
- **Additional System Configurations**

- 

sudo dnf upgrade --refresh
sudo dnf -y groupupdate core
sudo dnf install -y rpmfusion-free-release-tainted
sudo dnf install -y rpmfusion-nonfree-release-tainted 
sudo dnf install -y dnf-plugins-core

curl -o setup-repos.sh https://raw.githubusercontent.com/webmin/webmin/master/setup-repos.sh
sh setup-repos.sh
dnf install webmin

# Update the package manager's repository information
sudo dnf update -y

# Install prerequisites
sudo dnf install -y compat-openssl10 libcurl libicu

# Download PowerShell Core
wget https://github.com/PowerShell/PowerShell/releases/download/v7.2.2/powershell-7.2.2-linux-x64.tar.gz

# Extract the downloaded tarball
tar -xvf powershell-7.2.2-linux-x64.tar.gz

# Change into the extracted directory
cd powershell-7.2.2-linux-x64

# Start PowerShell Core
./pwsh


## Windows VS Linux
   - Ads versus no Ads, simple as

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
- **Update Package Manager and Repositories**
- **Software Installation**
- **Firewall Configuration**
- **Directory Creation and Permissions**
- **Additional System Configurations**
   - `sudo dnf update -y && sudo dnf upgrade --refresh -y`
   - `sudo dnf install https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm`
   - `sudo dnf install https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm`
   - sudo dnf install dnf-plugins-core
   - sudo dnf config-manager --add-repo https://download.docker.com/linux/fedora/docker-ce.repo
   - sudo dnf install docker-ce docker-ce-cli containerd.io
   - sudo systemctl start docker
   - sudo docker run hello-world
   - sudo docker down hello-world and remove
   - docker-compose logs -f -t
   - sudo systemctl enable docker
   - systemctl is-active docker
   - sudo dnf install -y sen
   - sen
   - Usage
Run sen from your terminal:

$ sen
(sen requires access to docker, you may need to run it with root privileges if your user cannot access docker)

Then you will be presented with list of all your containers and images. You can navigate via arrows. Sample commands are:

s — start a container
t — stop a container
d — delete a container or an image
f — follow logs of a container
l — get all logs of a container
i — inspect a container or an image
For more commands, type h to access help page.

6. **Software Installation**
   - `sudo dnf install xrdp neofetch qemu @Virtualization ffmpeg --allowerasing python3-pip baobab timeshift dnfdragora cockpit`
   - `pip3 install youtube-dl`
   - steam, chrome, office (equivalent) vscode virtual machine mananger powershell

7. **Firewall Configuration**
   - `sudo firewall-cmd --add-port=3389/tcp --permanent`
   - `sudo firewall-cmd --add-service=cockpit --permanent`
   - `sudo firewall-cmd --reload`

8. **Directory Creation and Permissions**
   - `cd /`
   - `sudo mkdir yourfolder`
   - `sudo chown -R $(whoami):$(id -gn $(whoami)) yourfolder`
   - mount your shares to a central location 


9. **Additional System Configurations**
   # systemctl status zram-swap
dnf install zram-generator-defaults zram-generator
systemctl enable zram-swap.service
systemctl start zram-swap.service
run a cmd to determine it's live?
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

add plex to your port forwaring table
#Choose your desktop flavor!
https://fedoraproject.org/spins/
cinnamon for modern linux UI
plasma for a modern UI that combines windows and linux

dnf grouplist -v hidden | grep Desktop

# Windows to Linux Transition Guide

Welcome to the Windows to Linux transition guide! This guide will walk you through the process of migrating from Windows to Linux using a powerful PowerShell script. Linux offers speed, security, and efficiency advantages, and this script will help you make the switch seamlessly.

## Table of Contents

1. [Introduction](#introduction)
2. [Before You Begin](#before-you-begin)
3. [Getting Started](#getting-started)
4. [Running the Script](#running-the-script)
5. [Customizing Your Linux Environment](#customizing-your-linux-environment)
6. [Conclusion](#conclusion)

## Introduction

In this guide, we'll show you how to transition from Windows to Linux using a single, powerful PowerShell script. You'll discover how Linux can provide a faster and more secure computing experience.

## Before You Begin

Before you begin the transition, here are a few important considerations:

- Backup your important data from your Windows system.
- Make a list of the software and applications you use regularly on Windows.

## Getting Started

### 1. Download the PowerShell Script

Visit [link_to_script_repository] to download the PowerShell script for the transition.

### 2. Prepare Your Linux Environment

- Ensure you have a Linux distribution installed on your system. [Choose your Linux distribution](https://fedoraproject.org/spins/).
- Open a terminal on your Linux system.

## Running the Script

### 3. Run the PowerShell Script

Navigate to the directory where you downloaded the PowerShell script and execute it using the following command:

```powershell
./transition-script.ps1 -param1 value1 -param2 value2

# Docker Compose Configuration
# Version: 3.8
#
# Services Included:
# - Cloudflared: Establishes a secure tunnel for services.
# - Plex: Media server for streaming movies and shows.
# - SABnzbd: Binary newsreader for downloading content.
# - Prowlarr: Indexer manager for Usenet and torrents.
# - Radarr: Movie collection manager for Usenet and BitTorrent users.
# - Radarr4K: Separate instance of Radarr for 4K content management.
# - Sonarr: Series collection manager for Usenet and BitTorrent users.
# - TDarr: Media transcoding server and node setup.
# - Overseerr: Media request and management tool.
# - Tautulli: Analytics and monitoring for Plex servers.
# - Homarr: Dashboard for self-hosted services.
# - Dash: Container displaying hardware information.
# - Notifiarr: Client for centralized notifications and automation.
# - HomeAssistant: Home automation platform.
#
# Volume Configurations:
# Persistent volumes are defined for each service to ensure data retention and management.
#
# Network Settings:
# Port mappings are provided for external access to services.
# Network mode is set to 'host' for certain services to facilitate network communication.
#
# Environment Variables:
# - PUID, PGID, TZ: Used for user, group identification, and time zone settings across services.
# - CLOUDFLARE_TOKEN, ADVERTISE_IP, PLEX_CLAIM, and other specific variables are set per service requirements.
#
# Restart Policy:
# A variable $RESTARTPOLICY controls the restart behavior of all services.
#

version: '3.8'

services:
    #cloudflared:
    #    image: cloudflare/cloudflared:latest
    #    container_name: cloudflared
    #    command: tunnel run
    #    environment:
    #    - TUNNEL_TOKEN=$CLOUDFLARE_TOKEN
    #    restart: $RESTARTPOLICY

    plex:
        image: plexinc/pms-docker:latest
        container_name: plex
        restart: $RESTARTPOLICY
        network_mode: host
        environment:
        - PUID=$PUID
        - PGID=$PGID
        - TZ=$TZ
        - ADVERTISE_IP=http://192.168.100.1:32400/
        - PLEX_CLAIM=claim-kYaicF7_oLugHcfVsder
        - HOSTNAME=YourPlexRequest
        devices:
        - /dev/dri:/dev/dri # Binds the Intel Quicksync decoder to Plex HW Transcode
        volumes:
        - plex_config:/config
        - /media/movies:/movies
        - /media/4Kmovies:/4Kmovies
        - /media/shows:/shows
        healthcheck:
            test: curl --fail http://192.168.100.1:32400/web/index.html || exit 1
            interval: 60s
            retries: 5
            start_period: 20s
            timeout: 10s

    sabnzbd:
        image: lscr.io/linuxserver/sabnzbd:latest
        container_name: sabnzbd
        environment:
        - PUID=$PUID
        - PGID=$PGID
        - TZ=$TZ
        volumes:
        - sabnzbd_config:/config
        - /terabytetemp/downloads:/downloads
        - /terabytetemp/incompletedownloads:/incomplete-downloads
        ports:
        - 9001:8080
        restart: $RESTARTPOLICY

    prowlarr:
        image: lscr.io/linuxserver/radarr:latest
        container_name: radarr
        environment:
        - PUID=$PUID
        - PGID=$PGID
        - TZ=$TZ
        volumes:
        - prowlarr_config:/config
        ports:
        - 9002:9696
        restart: $RESTARTPOLICY

    radarr:
        image: lscr.io/linuxserver/radarr:latest
        container_name: radarr
        environment:
        - PUID=$PUID
        - PGID=$PGID
        - TZ=$TZ
        volumes:
        - radarr_config:/config
        - /media/movies/Movies:/movies
        - /terabytetemp/downloads:/downloads
        ports:
        - 9003:7878

    radarr4K:
        image: lscr.io/linuxserver/radarr:latest
        container_name: radarr4K
        environment:
        - PUID=$PUID
        - PGID=$PGID
        - TZ=$TZ
        volumes:
        - radarr4k_config:/config
        - /media/movies/Movies:/movies
        - /terabytetemp/downloads:/downloads
        ports:
        - 9004:7878
        restart: $RESTARTPOLICY

    sonarr:
        image: lscr.io/linuxserver/sonarr:latest
        container_name: sonarr
        environment:
        - PUID=$PUID
        - PGID=$PGID
        - TZ=$TZ
        volumes:
        - sonarr_config:/config
        - /media/shows/Shows:/shows
        - /terabytetemp/downloads:/downloads
        ports:
        - 9005:8989
        restart: $RESTARTPOLICY

    tdarr:
        container_name: tdarr
        image: ghcr.io/haveagitgat/tdarr:latest
        restart: $RESTARTPOLICY
        environment:
        - PUID=$PUID
        - PGID=$PGID
        - TZ=$TZ
        - serverIP=0.0.0.0
        - serverPort=8266
        - webUIPort=8265
        - internalNode=true
        - inContainer=true
        - ffmpegVersion=6
        - nodeName=MyInternalNode
        ports:
        - 9006:8265 # webUI port
        - 9007:8266 # server port
        volumes:
        - tdarr_server:/app/server
        - tdarr_configs:/app/configs
        - tdarr_logs:/app/logs
        - /media/movies/Movies:/movies
        - /media/shows/Shows:/shows
        - /terabytetemp/tdarr/!cache:/tdarrcache
        devices:
        - /dev/dri:/dev/dri # for QSV

    tdarr-node:
        container_name: tdarr-node
        image: ghcr.io/haveagitgat/tdarr_node:latest
        restart: $RESTARTPOLICY
        environment:
        - PUID=$PUID
        - PGID=$PGID
        - TZ=$TZ
        - nodeName=MyExternalNode
        - serverIP=0.0.0.0
        - serverPort=9007
        - inContainer=true
        - ffmpegVersion=6
        volumes:
        - tdarrnode_server:/app/server
        - tdarrnode_configs:/app/configs
        - tdarrnode_logs:/app/logs
        - /terabytetemp/tdarr/movies:/movies
        - /terabytetemp/tdarr/shows:/shows
        - /terabytetemp/tdarr/!cache:/temp
        devices:
        - /dev/dri:/dev/dri # for QSV

    overseerr:
        image: sctx/overseerr:develop
        container_name: overseerr
        environment:
        - PUID=$PUID
        - PGID=$PGID
        - TZ=$TZ
        volumes:
        - overseerr_config:/app/config
        ports:
        - 9008:5055
        restart: $RESTARTPOLICY

    tautulli:
        image: ghcr.io/tautulli/tautulli:latest
        container_name: tautulli
        environment:
        - PUID=$PUID
        - PGID=$PGID
        - TZ=$TZ
        volumes:
        - tautulli_config:/config
        ports:
        - 9009:8181
        restart: $RESTARTPOLICY

    homarr:
        image: ghcr.io/ajnart/homarr:latest
        container_name: homarr
        environment:
        - PUID=$PUID
        - PGID=$PGID
        - TZ=$TZ
        #- EDIT_MODE_PASSWORD=$HOMARRPASSWORD
        volumes:
        - homarr_configs:/app/data/configs
        - homarr_data:/data
        - homarr_icons:/app/public/icons
        ports:
        - 9010:7575
        restart: $RESTARTPOLICY

    dash:
        image: mauricenino/dashdot:latest
        container_name: dash
        restart: $RESTARTPOLICY
        privileged: true
        ports:
        - 9011:3001
        volumes:
        - /:/mnt/host:ro

    notifiarr:
        container_name: notifiarr
        image: golift/notifiarr
        environment:
        - PUID=$PUID
        - PGID=$PGID
        - TZ=$TZ
        ports:
        - 9012:5454
        volumes:
        - notifiarr_config:/config
        restart: $RESTARTPOLICY
    
    homeassistant:
        image: ghcr.io/home-assistant/home-assistant:stable
        container_name: homeassistant
        environment:
        - PUID=$PUID
        - PGID=$PGID
        - TZ=$TZ
        ports:
        - 9013:8123
        volumes:
        - homeassistant_config:/config
        - /etc/localtime:/etc/localtime:ro
        - /run/dbus:/run/dbus:ro
        privileged: true
        restart: $RESTARTPOLICY
        # devices:
        # - /dev/ttyUSB0:/dev/ttyUSB0

    wizarr:
        container_name: wizarr
        image: ghcr.io/wizarrrr/wizarr
        environment:
        - PUID=$PUID
        - PGID=$PGID
        - TZ=$TZ
        ports:
        - 9014:5690
        volumes:
        - wizarr_config:/data/database
volumes:
  plex_config:
  sabnzbd_config:
  prowlarr_config:
  radarr_config:
  radarr4k_config:
  sonarr_config:
  tdarr_server:
  tdarr_configs:
  tdarr_logs:
  tdarr_cache:
  tdarrnode_server:
  tdarrnode_configs:
  tdarrnode_logs:
  tdarr_movies:
  tdarr_shows:
  tdarr_temp:
  overseerr_config:
  tautulli_config:
  homarr_configs:
  homarr_data:
  homarr_icons:
  notifiarr_config:
  homeassistant_config:
  wizarr_config:

sudo dnf copr enable kwizart/fedy
sudo dnf install fedy -y

sudo dnf install steam

flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo

sudo nano /etc/dnf/dnf.conf
max_parallel_downloads=10

sudo dnf install vlc

sudo hostnamectl set-hostname "New_Custom_Name"

sudo dnf -y groupupdate sound-and-video

sudo dnf install -y fira-code-fonts 'mozilla-fira*' 'google-roboto*'

sudo rpm -i https://downloads.sourceforge.net/project/mscorefonts2/rpms/msttcore-fonts-installer-2.6-1.noarch.rpm

sudo dnf install -y unzip p7zip p7zip-plugins unrar

sudo dnf install -y audacity 
flatpak install flathub org.audacityteam.Audacity

sudo dnf install -y gimp 
flatpak install flathub org.gimp.GIMP

flatpak install flathub com.simplenote.Simplenote

flatpak install flathub com.spotify.Client

flatpak install flathub org.standardnotes.standardnotes

flatpak install flathub com.obsproject.Studio

sudo dnf install -y gparted

Upon first use, a prompt appears at the top to enable Third Party Software Repositories. This option was also available in the initial Welcome screen. The option is additionally available in the hamburger menu (the three stacked lines) in the upper right corner. Select that menu and choose Software Repositories.

switch to your UI
sudo dnf -y install switchdesk switchdesk-gui

# Windows To Linux Transition Guide

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

##Welcome to the "Windows To Linux Transition Guide". 

### 1. Introduction

This guide is for anyone looking to transition from Windows to Linux, providing necessary insights and tools for a seamless switch. Tailored for power users, developers, or those just starting with Linux, it focuses on delivering practical knowledge for effective system management.

The move to Linux is often driven by the need for greater control over your computing environment, particularly in areas of privacy and autonomy. Windows users increasingly encounter issues like intrusive ads and concerns over data privacy. Linux stands as a viable alternative, offering an environment where your information is under your control, free from the commercial constraints often seen in other operating systems.

This guide will equip you with a thorough understanding of Linux basics and essential skills for system management. You'll learn to navigate the Linux environment effectively, leveraging its capabilities to meet your needs.
