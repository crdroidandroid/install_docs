# From Stock

## YOU NEED A PC OR LAPTOP
* Backup your data
* Make sure to be on latest Firmware!!!
* Go to Settings
* Scroll down
* Tap on "About phone"
* Go on "Software information"
* Tap Build number 7 - 8 times
* If needed input your Lock method
* Go back twice
* Go on "Developer options"
* Hit "OEM unlocking"
* Follow steps from popups
* Shut down Phone 
* On your PC your PC you make sure to have 7-Zip installed
* Right click on ["recovery.img"](https://sourceforge.net/projects/crdroid/files/crownlte/9.x/recovery.img/download)
* Make sure the file name is EXACTLY "recovery.img"
* Hover over 7-Zip and click on "add to archive"
* Select "tar" as the archive format and hit "OK"
* Download [Odin from here](https://odindownload.com/download/Odin3_v3.14.4.zip), if you havent already
* Extract that Archive
* After done go to Download mode (Volume - + Bixby + Power)
* Add the previously created .tar by clicking on AP and searching the location of where its saved.

## NOW YOU GONNA BE FAST
* Prepare to hold volume up + Bixby + Power instantly after pressing start
* Press start when you are ready
* Now you are in crDroid recovery!
* Go to "Factory Reset" and click "Format System"
* Do the same with Format Data

# From other AOSP rom
* Follow the guide on ["How to install ADB on your PC"](https://telegra.ph/HOW-TO-3-04-18) 
* Reboot to Recovery
* Go to Advanced
* Tap "Enter Fastboot"
* On PC open a Terminal of your choice
```
fastboot flash RECOVERY/recovery (depending on how new your recovery is, try both) path/to/recovery.img
```

# From TWRP
* Put recovery.img where you can find it
* Hit install and "Install Image"
* Go to wherever you put the image and click on it
* Select recovery and swipe to flash
* Go to reboot and "Reboot to Recovery"

# First time installation (clean flash) via PC:

* Make sure to have everything downloaded you want to use on your phone
  - crDroid
  - [GAPPS](http://downloads.codefi.re/jdcteam/javelinanddart/gapps) <- Select 13.0.0-arm64 packages
  - [MAGISK](https://github.com/programminghoch10/Lygisk#downloads) <- Lygisk is a way to keep root after update, you can use normal magisk tho
* Follow the guide on ["How to install ADB on your PC"](https://telegra.ph/HOW-TO-3-04-18) 
* On Recovery go to "Apply Update" and select "Apply from ADB"
* On PC start a Terminal of your choice and enter
```
adb sideload crDroid.zip
```
* |*OPTIONAL*| On Recovery go to "Apply Update" and select "Apply from ADB"
```
adb sideload gapps.zip
```
* |*OPTIONAL*| On Recovery go to "Apply Update" and select "Apply from ADB"
```
adb sideload magisk.zip
```
* Now in recovery go to factory reset and Format Data once more. If asked select F2FS
* Reboot to System

# First time installation (clean flash) via OTG/SDCARD:

* Make sure to have everything downloaded you want to use on your phone
  - crDroid
  - [GAPPS](http://downloads.codefi.re/jdcteam/javelinanddart/gapps) <- Select 13.0.0-arm64 packages
  - [MAGISK](https://github.com/programminghoch10/Lygisk#downloads) <- Lygisk is a way to keep root after update, you can use normal magisk tho

* Move everything you downloaded to an USB stick/HDD/SSD/Whatever formatted as exFat/Fat32
* Plug it into your phone while its off
* Hold Volume up + bixby + power
* Go to "Apply Update"
* If you werent too fast, your storage device should show up now.
  - if not go back and retry for a few times

### Update installation:
#### Via recovery (recommended way):
* Boot to recovery
* Choose apply update and Apply from ADB
* Now install crDroid zip via sideload and reboot

```
adb sideload crDroid.zip
```
* If you had gapps or Magisk, reboot to recovery and sideload gapps.zip/magisk.zip and reboot to System

#### Via OTA:
* Go to Settings -> System -> Updater and download latest build
* Choose install and let it finish
* If you had gapps or Magisk, reboot to recovery and sideload gapps.zip/magisk.zip and reboot to System
* Reboot