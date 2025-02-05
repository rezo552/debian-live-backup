# unattended-linux
Builds a Debian 10 (Buster) Live x86-64 ISO monthly using GitHub Actions. Used primarily for backing up and restoring Linux and Windows based systems. (You can use it in an unattended way, see the Confiugration Options)


## Default Password
The default username and password is root / toor.


## Installation Options
1. Burn / mount the ISO
2. Copy the files to a FAT32 formatted USB drive
    * Only works on modern UEFI based systems
3. Use `dd` to flash the ISO to a USB drive
    * Would only recommend for older BIOS based systems

## Configuration Options
This USB key is designed to autostart a script on launch so that you can run it in an unattended way. In the root folder of your USB key there is an autostart script, you can put your script inside that file if you are running it in an isolated environment. If the device is connected to the internet it is better to use the default script which can download machine-specific custom startup script from your private Github repo. The filename should match to the serial number of your mainboard (you can retrieve it after the first boot with "dmidecode -t baseboard | grep 'Serial Number'" command). In order to access your private repo you need to create an API token and insert it into the autostart file. 

## Tools

cifs-utils - Mount `Samba` and `Windows` file shares

ddrescue - Backup and restore failing drives

gdisk - `gpt` compatible `fdisk` toolset

nfs-common - mount `nfs` file shares

ntfs-3g - Manage `NTFS` formatted drives

wimtools - Create, restore, and manage `WIM` files for Windows based systems.



## Installed Packages
* apt-utils
* bash-completion
* cifs-utils
* curl
* dbus
* dmidecode
* dosfstools
* firmware-linux-free
* gddrescue
* gdisk
* iputils-ping
* isc-dhcp-client
* less
* linux-image-amd64
* live-boot
* nfs-common
* ntfs-3g
* openssh-client
* open-vm-tools
* procps
* systemd-sysv
* vim
* wimtools
* wget

For a full list of installed packages, see `packages.txt` in the release.




## References
This image is a fork of https://github.com/dpowers86/debian-live which was built based on https://willhaley.com/blog/custom-debian-live-environment/
