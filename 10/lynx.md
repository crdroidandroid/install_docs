### Pre-installation:

* Make sure you are on latest Pixel firmware installed
* Recovery vendor_boot.img (from download page, recovery button)
* Gapps (get it on [release page](http://nikgapps.com/ionutgherman) from their sourceforge)
* Optional KernelSU apk (get it on [release page](https://github.com/tiann/KernelSU/releases) from their GitHub - click "show all assets" to see the apk)

### First time installation (clean flash):

* On your computer open Command Prompt or Terminal and go to ADB folder location
* Reboot phone to fastboot with adb reboot bootloader
* Flash crDroid Recovery with command:

```
fastboot flash vendor_boot vendor_boot.img
```
*  fastboot will flash recovery to active slot
*  With volume buttons, go to Recovery Mode
*  In crDroid Recovery, go to Apply update - Apply from ADB
*  After that execute this command:

```
adb sideload zip_name.zip (where zip_name is crDroid zip for your device)
```
* After ROM installation finished, recovery will ask you to switch to the opposite slot to flash Gapps and/or Magisk. Select yes.
* After reboot to recovery, adb sideload Gapps and/or Magisk.
* Reboot to recovery
* After reboot - Factory reset.
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
* Use Updater to update to latest version. Gapps and Magisk (if installed) are being kept

### Update installation:
#### Via OTA:
* Use Updater to update to latest version. Gapps and Magisk (if installed) are being kept no need to flash agagin 
* Go to Settings -> System -> Updater and download latest build
* Choose install and let it finish
* Reboot
