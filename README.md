# Preseed Configuration Files for DebianInstaller

## Description
One of The Debian Project's most powerful features is the ability to customize and automate installations using the DebianInstaller system. Many [Debian-based](https://debian.org) GNU/Linux distributions, including Ubuntu, use DebianInstaller (or some derivitative) for system installation. The configuration file to customize and automate the DebianInstaller is known as a preseed file. This repository includes customized preseed files for use at FreeGeek Chicago. YMMV.


## Files
* xubuntu1204.seed Preseed file for Xubuntu 12.04


## Setup Order Ubuntu 12.04
* [Select a language]
* [Select your location]
* [Configure the keyboard] Detect Layout
* [Configure the keyboard] Country of origin
* [Configure the keyboard] Keyboard layout
* [Configure the network]  Hostname
* [Choose a mirror]  Ubuntu Country of Origin
* [Choose a mirror of the..]  Ubuntu archive mirror: us.archive.ubuntu.com
* [Choose a mirror of the..]  HTTP Proxy Information

* [Setup users and passwords] Full name
* [Setup users and passwords] Username
* [Setup users and passwords] Password 1
* [Setup users and passwords] Password 2
* [Setup users and passwords] Encrypt Home?

* [Configure the clock] Time zone
* [Partition disks] Partitioning Method: Guided, use entire disk
* [Partition disks] Which disk?
* [Partition disks] Write changes?

## Using the Linux Mint 19.1 Preseed on a USB drive
* Create a normal linuxmint USB drive or use one that already works
* Open the contents of the usb drive
* You will find a file 'linuxmint.seed' in the preseed folder; Replace /preseed/linuxmint.seed with the linuxmint.seed in this git repository.
* Open the /isolinux/isolinux.cfg in your USB drive with you test editor of choice
* In this file look at the part that says 'label oem'. Indented under it is a line that starts with 'append'. Look for for 'only-ubiquity' in this line and change it to 'automatic-ubiquity'. It should look like this:
```
label oem
  menu label OEM install (for manufacturers)
  kernel /casper/vmlinuz
  append file=/cdrom/preseed/linuxmint.seed oem-config/enable=true automatic-ubiquity boot=casper initrd=/casper/initrd.lz quiet splash --
 ```
* Save the file and test if the USB stick works. It should take a while. Make sure you are connected to the internet!!
## Online Resources
* [Debian Installer](http://wiki.debian.org/DebianInstaller/)
* https://help.ubuntu.com/12.04/installation-guide/i386/preseed-intro.html
* https://help.ubuntu.com/12.04/installation-guide/i386/appendix-preseed.html
* https://help.ubuntu.com/12.10/installation-guide/i386/preseed-using.html#preseed-auto
* [An Example of Preseed](https://help.ubuntu.com/lts/installation-guide/example-preseed.txt) from [ubuntu.com](https://ubuntu.com).
