### Pre-installation:

* Make sure you are on the latest stable Android 16 firmware. Use [Android Flash Tool](https://flash.android.com/) to install if not on it
* Necessary files to install crDroid (from download page, select "Download older versions")
* Gapps ([my Nikgapps variants](https://nikgapps.com/ionutgherman) optimized for Pixels or [official NikGapps variants](https://nikgapps.com/downloads))
* KernelSU Next is integrated, install KernelSU Next apk from here: [KernelSU Next](https://github.com/KernelSU-Next/KernelSU-Next/releases/download/v1.0.9/KernelSU_Next_v1.0.9_12797-release.apk)

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
* After ROM installation finished, recovery will ask you to switch to the opposite slot to flash Gapps. Select yes.
* After reboot to recovery, adb sideload Gapps.
* Reboot to recovery
* After reboot -> Factory reset.
* Reboot and enjoy

###  Dirty flash via recovery:
* On your computer open Command Prompt or Terminal and go to ADB folder location
* Reboot into Recovery using adb reboot recovery
* In crDroid Recovery, go to Apply update -> Apply from ADB
* After that execute this command:

```
adb sideload zip_name.zip (where zip_name is crDroid zip for your device)
```
* After ROM installation finished, recovery will ask you to switch to the opposite slot to flash Gapps. Select yes.
* After reboot to recovery, adb sideload Gapps.
* Reboot and enjoy

### Update installation:
#### Via OTA:
* Use Updater to update to the latest version. Gapps (if installed) are being kept
* If newer version of NikGapps was released, use dirty flash to update the ROM and Gapps also, don't use Updater, you cannot update Gapps with Updater
* Go to Settings -> System -> Updater and download latest build
* Choose install and let it finish
* Reboot
