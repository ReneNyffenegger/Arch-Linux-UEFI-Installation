# Arch-Linux-UEFI-Installation
Scripts for an installation of Arch Linux with UEFI firmware.

# Preparation

## 1. Clone this repository to USB stick

    cd /media/rene/1C51-C5A2
    git clone https://github.com/ReneNyffenegger/Arch-Linux-UEFI-Installation
    cd
    umount /dev/sdb1

## 2. Start Arch Linux live CD

Insert the Ach Linux live CD into the computer where Arch Linux is to be installed.

Start computer.

## 3. Mount USB Stick on PC

Insert USB stick, then

    mkdir /media
    mount -o umask=000 /dev/sdb1 /media
    cd /media/Arch-Linux-UEFI-Installation

## 4. Set a few environment variables


    export WIFI_ESSID=essid
    export WIFI_PASSWORD=secret

## 5. Start first script

    ./01-before-chroot.sh
   
## 6. chroot to /mnt

    cd /
    umount /dev/sdb1
    arch-chroot /mnt /bin/bash

## 7. mount USB stick again

    mount -o umask=000 /dev/sdb1 /mnt

## 8. start second script

    cd /mnt/Arch-Linux_UEFI-Installation
    ./02-after-chroot.sh
