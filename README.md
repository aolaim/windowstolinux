# /windowstolinux
- **Windows VS Linux**
- **Linux File Structure**
- **Software Installation**
- **Firewall Configuration**
- **Directory Creation and Permissions**
- **Additional System Configurations**
sudo dnf config-manager --add-repo https://dl.winehq.org/wine-builds/fedora/34/winehq.repo
sudo dnf install wine
sudo dnf install winetricks

wine setup.exe
wine notepad.exe

#!/bin/bash

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
