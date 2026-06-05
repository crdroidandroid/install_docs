### Pre-installation:

* Make sure you are on latest Pixel firmware installed. Use [Android Flash Tool](https://flash.android.com/) to install if not on it
* [Recovery vendor_boot.img](https://sourceforge.net/projects/crdroid/files/panther/12.x/recovery/)
* A computer with the Android Platform Tools installed. See XDA's guide for installing the platform tools [here](https://www.xda-developers.com/install-adb-windows-macos-linux/)
* Optional Gapps ([my Nikgapps variants](http://nikgapps.com/ionutgherman) optimized for Pixels or [official NikGapps variants](https://nikgapps.com/downloads))
* Optional Magisk APK (get it on [release page](https://github.com/topjohnwu/Magisk/releases) from their GitHub)

### First time installation (clean flash):

* On your computer open Command Prompt or Terminal and go to Platform Tools folder location
* Reboot phone to fastboot with:

```
adb reboot bootloader
```
* Flash crDroid Recovery with command:

```
fastboot flash vendor_boot vendor_boot.img
```
* fastboot will flash recovery to active slot
* With volume buttons, go to Recovery Mode
* In crDroid Recovery, go to Apply update - Apply from ADB
* After that execute this command:

```
adb sideload zip_name.zip (where zip_name is crDroid zip for your device)
```
* After ROM installation finished, recovery will ask you to switch to the opposite slot to flash Gapps and/or Magisk. If you downloaded them before, select yes.
* (Optional) After reboot to recovery, adb sideload Gapps and/or Magisk.
* Factory reset.
* Reboot and enjoy

###  Dirty flash  via recovery:
* On your computer open Command Prompt or Terminal and go to ADB folder location
* Reboot into Recovery using:

```
adb reboot recovery
```
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
* Use Updater to update to latest version. Gapps and Magisk (if installed) are being kept no need to flash again 
* Go to Settings -> System -> Updater and download latest build
* Choose install and let it finish
* If using Magisk, install to inactive slot in the manager
* Reboot