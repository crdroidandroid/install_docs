### Pre-installation:

* Make sure you have latest firmware available for your country.
* Gapps package (optional) (from download page, gapps button)
* Recovery (from download page, recovery button)
* A pc with platform-tools working (adb/fastboot)

### First time installation (clean flash):

* Unlock Bootloader
* Reboot Fastboot
* fastboot flash boot boot.img
* fastboot flash vendor_boot vendor_boot.img
* fastboot reboot recovery
* Now in recovery go to factory reset and confirm the reset
* Choose apply update and Apply from ADB
* Now install crDroid zip via sideload

```
adb sideload crDroid.zip
```
* When asked to sideload gapps, choose 'Yes' to reboot to recovery or 'No' if you don't want gapps and want to reboot to system
* Now if you choosed to install gapps, simply sideload gapps.zip the same way you installed crDroid.zip then reboot to system

### Update installation:
#### Via recovery (recommended way):
* Boot to recovery
* Choose apply update and Apply from ADB
* Now install crDroid zip via sideload and reboot

```
adb sideload crDroid.zip
```
* If you had gapps, reboot to recovery and sideload gapps.zip and reboot

#### Via OTA:
* Go to Settings -> System -> Updater and download latest build
* Choose install and let it finish
* If having gapps, reboot to recovery and sideload gapps package again
* Reboot
