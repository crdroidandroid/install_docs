### Pre-installation:

* Make sure you are on the May 2025 firmware or newer
* Necessary files to install crDroid (from download page, select "Download older versions)
* Gapps ([my Nikgapps variants](https://nikgapps.com/ionutgherman) optimized for Pixels or [official NikGapps variants](https://nikgapps.com/downloads))
* Optional if you want root, install Magisk Kitsune (get it on [release page](https://github.com/1q23lyc45/KitsuneMagisk/releases) from their GitHub - click on "Assets" and download app-release.apk)

#### Be sure that you are on May 2025 build or newer. If not, go to [flash.android.com](https://flash.android.com) and install May 2025 or newer build and follow the steps from there. Important thing from here is to let the check ON for "Force flash all partitions". This step is for clean install coming from stock ROM.
#### If you are running custom ROM and coming from April 2025 or lower, you need to follow these steps to be sure that you will not break your device!!!

* Download bootloader and radio image from your device recovery folder from download page
* On your computer open Command Prompt or Terminal and go to ADB/fastboot folder location:
* Install May 2025 bootloader and radio image by following these commands:
```
fastboot flash bootloader bootloader-shiba-ripcurrent-15.3-13272266.img --slot all
fastboot flash radio radio-shiba-g5300i-241205-250127-b-12973597.img --slot all
fastboot reboot bootloader
```
* After the installation is done, device will reboot to bootloader and you can proceed to the next steps, like CLEAN FLASH or DIRTY FLASH, depends on what situation are you on in the present

#### ATTENTION!!! Do not use Updater to update May 2025 crDroid build if coming from April 2025 or lower because the active slot will not be flashed with newer bootloader version and if the device goes back to the active slot if the opposite fails to boot, your device will break! Be careful! Use CLEAN FLASH or DIRTY FLASH methods only!

* After May 2025, you will be able to install newer builds via OTA (aka Updater) because builds will not have anti-rollback anymore (and that depends if Google isn't doing another update that will implement anti-rollback protection again). Instructions will be updated accordingly if that will happen

#### NOTE!!! If you flash older crDroid versions (if you found them online somewhere else) or another ROM that has April Sec Patches or lower and break your device, I am not responsible for you not following the instructions and cannot blame me for your broken device!

### First time installation (clean flash):

* On your computer open Command Prompt or Terminal and go to ADB/fastboot folder location
* Reboot phone to fastboot with adb reboot bootloader
* Flash crDroid Recovery with command:

```
fastboot flash vendor_boot vendor_boot.img
```
* fastboot will flash recovery to active slot
* With volume buttons, go to Recovery Mode
* In crDroid Recovery, go to Apply update -> Apply from ADB
* After that execute this command:

```
adb sideload zip_name.zip (where zip_name is crDroid zip for your device)
```
* After ROM installation finished, recovery will ask you to switch to the opposite slot to flash Gapps and/or Magisk. Select yes.
* After reboot to recovery, adb sideload Gapps and/or Magisk.
* Reboot to recovery
* After reboot -> Factory reset.
* Reboot and enjoy

###  Dirty flash  via recovery:
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
