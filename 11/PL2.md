### Pre-installation:

* Recovery (from download page, recovery button)
* Optional gapps (from download page, gapps button)


### First time installation (clean flash):

* Backup your data to PC, OTG flash drive
* Boot to download mode and flash recovery

```
fastboot flash boot boot.img
```
* Now boot to recovery by holding VOL UP + POWER
* Navigate to Factory reset and format data, wipe cache and wipe system
* Now reboot to recovery
* Navigate to Apply update and choose from adb (if you have crDroid.zip on external sdcard, you may choose this option and navigate to where the zip is)
* Now sideload crDroid zip

```
adb sideload crDroid.zip
```
* If you are running with gapps, choose again to apply from adb and sideload gapps.zip
* Reboot to system

### Update installation:
#### Via recovery (recommended way):
* Boot to download mode and flash recovery

```
fastboot flash boot boot.img
```
* Boot to recovery by holding VOL UP + POWER
* Navigate to Apply update and choose from adb (if you have crDroid.zip on external sdcard, you may choose this option and navigate to where the zip is)
* Now install crDroid zip via sideload and reboot

```
adb sideload crDroid.zip
```

#### Via OTA:
* Go to Settings -> System -> Updater and download latest build
* Choose install and let it finish
* Reboot
