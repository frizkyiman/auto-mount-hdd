# Auto Mount HDD Script Openwrt
Auto Mount HDD on Openwrt

This script automates the process of mounting an NTFS-formatted external HDD on OpenWrt. It allows you to easily mount the HDD with custom options at a specified mount point.

**Features:**

* Checks if the mount point folder exists, and creates it if necessary.
* Unmount device before mounting.
* Mounts the NTFS-formatted HDD using the **'ntfs-3g'** driver.
* Provides flexibility to customize the device, mount point according to your requirements.


**Prerequisites:**

Before using this script, ensure that the **'ntfs-3g'** package is installed on your OpenWrt device. If it is not installed, you can install it using the following command:
```
opkg update
opkg install ntfs-3g
```

1. Install the script.
```
wget --no-check-certificate https://raw.githubusercontent.com/frizkyiman/auto-mount-hdd/main/mount_hdd -O /usr/bin/mount_hdd && chmod +x /usr/bin/mount_hdd
```

2. Run the script on terminal.
```
mount_hdd <DEVICE> <MOUNT_POINT>
```
Dont forget to input your Device and Mount Point here, eg. mount_hdd /dev/sda1 /nas-storage"

3. You can run this script at startup by adding this to /etc/rc.local
```
nano /etc/rc.local
```
```
mount_hdd <DEVICE> <MOUNT_POINT>
```

**Note:** Ensure that the HDD is properly connected and formatted with the NTFS filesystem.
