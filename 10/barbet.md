### Pre-installation:

* Ensure you are running the latest available ROM
* Optional gapps (from download page, gapps button)
* Recovery (from download page, Recovery button)
* Google platform-tools (adb/fastboot)


### First time installation (clean flash):

* Step 1: Unlock bootloader and enable adb through developer settings
* Step 2: On PC enter
```
adb reboot bootloader
```
* Step 3: Now type the following command to unlock the bootloader and flash required images:
```
fastboot flashing unlock
fastboot flash boot /path/to/boot.img
fastboot flash dtbo /path/to/dtbo.img
fastboot flash vendor_boot /path/to/vendor_boot.img
```
* Step 4: Using volume and power buttons, select "Reboot Recovery"
* Step 5: Wipe data. select Apply Update, then ADB sideload and type
```
adb sideload /path/to/ROM.zip
```
* Step 6: Reboot recovery and sideload any extras, then reboot device!

### Update installation:
* Step 1: boot phone into normal Android mode
* Step 2: Download update to phone or adb push from PC
* Step 3: Open Settings>System>Updater
* Step 4: Click the hamburger icon on the top right, then Local Update, and apply
* Step 5: Turn on caffeine or turn off screen lock, and stay on this page until reboot
**NOTICE: IF THE UPDATE DISAPPEARS OVER TIME DURING INSTALL, IT HAS COMPLETED. REBOOT MANUALLY THROUGH POWER MENU**
