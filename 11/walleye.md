### Pre-installation:
* Make sure you are on the latest stable Pixel firmware installed (A11)
* Download [TWRP](https://twrp.me/google/googlepixel2.html) and [repartition zip](https://sourceforge.net/projects/crdroid/files/walleye/11.x/recovery/) for Pixel 2 XL
* On your computer open Command Prompt or Terminal and go to ADB folder location
* Reboot phone to fastboot with adb reboot bootloader
* Boot TWRP with command:

```
fastboot boot twrp-3.3.0-0-walleye.img
```

* After TWRP booted, 'swipe to Allow Modifications'
* Go to Advanced -> ADB Sideload and sideload zip:

```
adb sideload productpartition-walleye-v14.zip
```

* After the zip is getting finished, will ask you to wipe data. Go to TWRP main page -- Wipe -- Format Data -- type yes and wipe
* After that, go to Reboot -> Bootloader

#### Note:
* If you want to revert to the stock partition table, flash the latest official [Google Pixel 2 factory image](https://developers.google.com/android/images#walleye)

### First time installation (clean flash):
#### Download:
* ROM (obviously)
* Recovery boot.img (from download page, recovery button)
* Gapps ([my Nikgapps variants](https://nikgapps.com/ionutgherman) optimized for Pixels or [official NikGapps variants](https://nikgapps.com/downloads))
* Optional if you want root, install Magisk Kitsune (get it on [release page](https://github.com/HuskyDG/magisk-files/releases) from their GitHub - click on "Assets" and download app-release apk)

#### Installation instructions:
* On your computer open Command Prompt or Terminal and go to ADB folder location
* Reboot phone to fastboot with adb reboot bootloader
* Flash crDroid Recovery with command:

```
fastboot flash boot boot.img
```

* fastboot will flash recovery to active slot
* With volume buttons, go to Recovery Mode
* In crDroid Recovery, go to Apply update - Apply from ADB
* After that execute this command:

```
adb sideload zip_name.zip (where zip_name is crDroid zip for your device)
```

* After ROM installation finished, recovery will ask you to switch to the opposite slot to flash Gapps and/or Magisk. Select yes.
* After reboot to recovery, adb sideload Gapps and/or Magisk.
* Reboot to recovery
* After reboot - Factory reset.
* Reboot and enjoy

###  Dirty flash via recovery:
* On your computer open Command Prompt or Terminal and go to ADB folder location
* Reboot into Recovery using adb reboot recovery
* In crDroid Recovery, go to Apply update - Apply from ADB
* After that execute this command:

```
adb sideload zip_name.zip (where zip_name is crDroid zip for your device)
```

* After ROM installation finished, recovery will ask you to switch to the opposite slot to flash Gapps and/or Magisk. Select yes.
* After reboot to recovery, adb sideload Gapps and/or Magisk.
* Reboot and enjoy

### Update installation:
#### Via OTA:
* Use Updater to update to latest version. Gapps (if installed) are being kept
* Go to Settings -> System -> Updater and download latest build
* Choose install and let it finish
* After OTA update finished, don't reboot yet, go to Magisk, press on Install and install to Inactive Slot (After OTA)
* Reboot
