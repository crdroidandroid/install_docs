### Pre-installation:

* **NOS stable based on Android 14 firmware is required**
* Optional gapps (from download page, gapps button)


### First time installation (clean flash):
* Boot to recovery
* Flash the provided recovery image and vendor boot image via fastboot using "fastboot flash recovery recover.img" & "fastboot flash vendor_boot vendor_boot.img"
* Reboot to recovery using either volume + and power button combo or via fastboot command
* Navigate to Apply Update > Apply from ADB
* adb sideload the lineage zip using "adb sideload crdroid-*-peridot.zip"
* Factory reset/format data
* Reboot to system
* In case you want to use your own google apps package nikkaGapps is recomended, you can install this by rebooting back into recovery after step 4

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
* Reboot
