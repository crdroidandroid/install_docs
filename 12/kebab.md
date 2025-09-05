### Pre-installation:

* **OnePlus8T - 14.1.0.602 firmware is required** (https://github.com/Wishmasterflo/Firmware_flasher?tab=readme-ov-file)
* Download dtbo, vbmeta, super_empty, recovery (from download page, recovery button)
* Optional gapps (from download page, gapps button)


### First time installation (clean flash):

* Backup your data to PC, OTG flash drive
* Make sure you are on 14.0.602 firmware 
* Now in recovery go to factory reset and confirm the reset
* Reboot to bootloader
* Fastboot flash vbmeta vbmeta.img
* Fastboot flash dtbo dtbo.img
* Fastboot wipe-super super_empty.img
* Fastboot flash recovery recovery.img
* Fastboot reboot recovery
* While in recovery, Wipe data/Factory reset
* While in recovery, navigate to Apply update -> Apply from ADB
* Now install crDroid zip via sideload

```
adb sideload crdroid.zip
```
* Go back to main menu and reboot to recovery to install gapps (if you don't want gapps, reboot to system)
* To install gapps, simply sideload gapps.zip the same way you installed crDroid.zip then reboot to system

### Update installation:

#### Via recovery (recommended way):
* Boot to recovery
* Choose apply update and Apply from ADB
* Now install crDroid zip via sideload and reboot

```
adb sideload crDroid.zip
```
* If you had gapps, reboot to recovery and sideload gapps.zip and reboot

#### Via OTA:
* Go to Settings -> System -> Updater and download latest build
* Choose install and let it finish
* Reboot
