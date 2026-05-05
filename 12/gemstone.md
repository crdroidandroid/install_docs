### Pre-installation:

* Unlocked bootloader
* Latest regional HyperOS firmware installed
* boot.img, vendor_boot.img & dtbo.img (from download page, recovery button)
* Optional gapps (from download page, gapps button)

### First time installation (clean flash):

* Backup your data to PC, OTG flash drive
* Boot to fastboot (volume down + power button)
* Flash boot, vendor_boot and dtbo 

```
fastboot flash boot boot.img
fastboot flash vendor_boot vendor_boot.img
fastboot flash dtbo dtbo.img
```

* Boot to crDroid recovery (volume up + power button)
* Format Data
* Sideload crDroid zip

```
adb sideload crDroid.zip
```

Normally, adb will report Total xfer: 1.00x, but in some cases, even if the process succeeds the output will stop at 47% and report adb: failed to read command: Success. In some cases it will report adb: failed to read command: No error or adb: failed to read command: Undefined error: 0 which is also fine.

### Install gapps (optional)
* Reboot to recovery
* Sideload gapps.zip

```
adb sideload gapps.zip
```
* Reboot to system

### Update:
#### Via OTA:
* Go to Settings -> System -> System updates
* Download latest build
* Choose install and let it finish
* Reboot (Don't reboot until reboot prompt OR if the update screen goes blank)
