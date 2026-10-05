### Pre-installation:

* Make sure you are on the latest stable Android 17 firmware. Use [Android Flash Tool](https://flash.android.com/) to install if not on it
* Necessary files to install crDroid (from download page, select "Download older versions")
* Gapps ([my 306Gapps variants](https://sourceforge.net/projects/ionut-306gapps/files/) optimized for the devices or you can create one for yourself from [306Gapps](https://github.com/306gapps/306gapps))
* The ROM is coming with blu_spark kernel, install blu_spark KSU mod to activate root: [blu_spark KSU mod](https://github.com/engstk/KernelSU/releases)

### First time installation (clean flash):

* On your computer open Command Prompt or Terminal and go to ADB/fastboot folder location
* Reboot phone to fastboot with adb reboot bootloader
* Flash crDroid Recovery with command:

```
fastboot flash vendor_boot boot.img
fastboot flash vendor_boot dtbo.img
fastboot flash vendor_boot vendor_boot.img
fastboot flash vendor_boot vendor_kernel_boot.img
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
* Go to Settings -> System -> System updates and download latest build
* Use System updates to update to the latest version. Gapps (if installed) are being kept
* If newer version of Gapps was released, use recovery to dirty flash ROM and Gapps to update them. You cannot update Gapps with System updates
* Before updating, go to System update preferences and enable "Prioritise update process". It speeds up the update but with the cost of device performance
* Choose install and let it finish
* Reboot
