# Archlinux Minimal Installation

## Installation

1. Make a bootable USB
1. Boot from USB
1. First steps
1. Customizing the installation process

### Make bootable USB

#### Get ISO image from archlinux web: 

To create a bootable archlinux usb
[Download a Archlinux bootable iso](https://www.archlinux.org/download/) image and write to a bootable USB device with this commands:

#### Write image to disk

```
# dd bs=4M if=/tmp/archlinux.iso of=/dev/sdh && sync
dd bs=4M if=/path/archlinux.iso of=/dev/sdX status=progress && sync
```

### First boot

Plug the created usb in the usb port of the new computer to be installed.

You must boot the new computer using UEFI mode. You must choose the F2/Del key to enter BIOS and configure UEFI boot or F11 key to choose UEFI partition of the USB device.

Now you have booted from USB your new computer and you have a prompt:

```bash 
root@archiso ~ #
```

#### Firts commands

1. The first command must be loadkeys. You can choose your correct layout for the keyboard:

```bash
loadkeys es
loadkeys fr
loadkeys uk
```

Theese are for spanish, french and british english. More info here: 
[Loadkeys](https://wiki.archlinux.org/index.php/Linux_console/Keyboard_configuration#Loadkeys)

2. The Second one must be passwd to change the root password.
3. The third, you must check the network is runnig ok.
4. The forth 
```bash 
systemctl start sshd
```

Starting the openssh server

### Remote Access
You must have remote access from the ansible host.
```bash
ssh root@mi.ip
# Optional: offending keys
# ssh-keygen -R mi.ip
ssh-copy-id root@mi.ip
ssh root@mi.ip

```

