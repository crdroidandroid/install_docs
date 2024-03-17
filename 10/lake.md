### Pre-installation:

* Recovery (from download page, recovery button)
* Optional gapps (from download page, gapps button)

### First time installation (clean flash):

* Backup your data to PC, OTG flash drive
* Boot to bootloader and flash recovery

```
fastboot flash boot boot-cr14.img
```
* Now boot to recovery by holding volumes
* Apply update from adb, flash copy-partitions (adb sideload copy-partitions-20210323_1922.zip)
* Now reboot to recovery
* Navigate to Apply update and choose from adb (if you have crDroid.zip on external sdcard, you may choose this option and navigate to where the zip is)
* Now sideload crDroid zip

```
adb sideload crDroid.zip
```
* If you are running with gapps, choose again to apply from adb and sideload gapps.zip
* Navigate to format data
* Reboot to system

### Update installation:
#### Via recovery (recommended way):
* Boot to recovery
* Navigate to Apply update and choose from adb (if you have crDroid.zip on external sdcard, you may choose this option and navigate to where the zip is)
* Now install crDroid zip via sideload and reboot

```
adb sideload crDroid.zip
```

#### Via OTA:
* Go to Settings -> System -> Updater and download latest build
* Choose install and let it finish
* Reboot
