### Pre-installation:

* Make sure your device is on the latest official firmware
* Download the ROM zip together with the recovery images (boot.img, dtbo.img and vendor_boot.img)
* Unlock the bootloader and enable USB debugging, then install adb and fastboot on your computer

### First time installation (clean flash):

* Reboot your device to bootloader (fastboot mode)
* Flash the recovery images with fastboot

```
fastboot flash boot boot.img
fastboot flash dtbo dtbo.img
fastboot flash vendor_boot vendor_boot.img
```
* Reboot to recovery

```
fastboot reboot recovery
```
* In recovery, choose "Apply update" > "Apply from ADB" and sideload the ROM

```
adb sideload crdroid.zip
```
* Once done, go back and perform a factory reset / wipe data (required for a clean flash)
* Optional: to install gapps, reboot to recovery again if needed, choose "Apply update" > "Apply from ADB" and sideload the gapps zip

```
adb sideload gapps.zip
```
* Reboot to system


### Update installation:

* Reboot to recovery
* Choose "Apply update" > "Apply from ADB" and sideload the new ROM zip
adb sideload crdroid.zip
```
* Reboot to system
