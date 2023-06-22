# Auto-Mount-HDD-Script-Openwrt
Auto Mount HDD on Openwrt using NTFS-3g

This script automates the process of mounting an NTFS-formatted external HDD on OpenWrt during system startup. It allows you to easily mount the HDD with custom options at a specified mount point.

**Features:**

* Checks if the mount point folder exists, and creates it if necessary.
* Mounts the NTFS-formatted HDD using the **'ntfs-3g'** driver.
* Provides flexibility to customize the device, mount point, and mount options according to your requirements.
* Suitable for automating the mounting process on OpenWrt systems using the init.d mechanism.

**Prerequisites:**

Before using this script, ensure that the **'ntfs-3g'** package is installed on your OpenWrt device. If it is not installed, you can install it using the following command:
```
opkg update
opkg install ntfs-3g
```

How To:
```
cd /etc/init.d/ && wget https://raw.githubusercontent.com/frizkyiman/Auto-Mount-HDD-Script-Openwrt/main/mount_hdd && chmod +x mount-hdd && /etc/init.d/mount-hdd enable
```

Step by step:

1. SSH into your OpenWrt device.
2. Move to the init.d directory:
   ```
   cd /etc/init.d/
   ```
3. Download the script from GitHub:
   ```
   wget https://raw.githubusercontent.com/frizkyiman/Auto-Mount-HDD-Script-Openwrt/main/mount_hdd -O mount-hdd
   ```
4. Make the script executable:
   ```
   chmod +x mount-hdd
   ```
5. Update the configuration variables in the script:
* Set the DEVICE variable to the appropriate device of your HDD (e.g., /dev/sda1).
* Set the UUID variable to the appropriate device of your HDD (e.g., 6239492739).
* Set the MOUNT_POINT variable to the desired mount point for your HDD (e.g., /nas-storage).
   ```
   nano /etc/init.d/mount-hdd
   ```
  (save with ctrl+x then Y then Enter)
  
6. Update the init script:
   ```
   /etc/init.d/mount-hdd enable
   ```
7. You can Reboot your OpenWrt device or directly run the script:
   ```
   /etc/init.d/mount-hdd start
   ```
   If it cannot mounted you should reboot or unmount the hdd first.
   ```
   reboot
   ```
9. After the reboot, the script will automatically mount the NTFS-formatted HDD at the specified mount point with the provided mount options.

**Note:** Ensure that the HDD is properly connected and formatted with the NTFS filesystem.
