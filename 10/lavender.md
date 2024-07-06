### Pre-installation:

* Recovery
* Rom
* GApps

### First time installation (clean flash):

* Backup your data to PC, OTG flash drive
* Boot to fastboot and flash recovery (Extract OrangeFox Zip)
* If you are coming from 4.4 based rom, change data/cache to F2FS
* If you are on latest firmware "V12.5.3.0" no need to flash it again

```
fastboot flash recovery.img
```
* Now boot to OrangeFox by holding VOL UP + POWER
* Untoggle "Unmount System before installing a ZIP
* Wipe system, vendor, cache & metadata partition
* Flash the crDroid (Ignore system mount error)
* Reboot to recovery and then flash GApps
* Factory Reset (Format data is recommended)
* Reboot to system

### Update installation:
#### Via recovery (recommended way):

* Boot to recovery
* Flash the update
* Wipe dalvik, cache
* Reboot and Enjoy

#### Via OTA:

* Go to Settings -> System -> Updater and download latest build
* Choose install and let it finish
* Reboot

### Troubleshooting:

* If it gives bootloop or keeps restarting in bootaniamtion, flash this cust image, and flash crDroid again: [Cust Image](https://drive.google.com/uc?id=1nTFGAjAkWSZTMlIAHyH62OgIW2ot_d0Z&export=download)
