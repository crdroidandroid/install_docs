### Pre-installation:

* Firmware is included in the ROM build (based on HyperOS 2)
* Optional GApps packages for Android 15 (arm64):
  * [MindTheGapps](https://github.com/MindTheGapps/15.0.0-arm64/releases/tag/MindTheGapps-15.0.0-arm64-20250214_082511)
  * [crDroid Elite NikGapps build](https://nikgapps.com/crdroid-official)

### First time installation (clean flash):

* Boot your device into fastboot mode
* Flash crDroid recovery:

```
fastboot flash recovery recovery.img
```
* Boot into recovery and format data (this will wipe all data)
* In recovery, tap on *Apply update* and sideload the latest ROM:

```
adb sideload crDroid-XX.0-fuxi-xxxxxxxx.zip
```
* When prompted whether to sideload GApps:
  * Choose **Yes** to reboot back into recovery and sideload GApps
  * Choose **No** to skip GApps and directly reboot to system
* If you chose **Yes**, sideload GApps package the same way:

```
adb sideload <gapps-package>.zip
```

### Update installation:

* Boot into crDroid recovery
* Sideload the latest crDroid ROM:

```
adb sideload crDroid-XX.0-fuxi-xxxxxxxx.zip
```
* (Optional) Reboot to recovery and sideload GApps if needed:

```
adb sideload <gapps-package>.zip
```
* Reboot to system

### OTA Update (alternative method):

* Go to **Settings -> System -> Updater** and download the latest build
* Tap **Install** and wait for the process to complete
* If you're using GApps:
  * Reboot to recovery after OTA finishes
  * Sideload your GApps package again:

```
adb sideload <gapps-package>.zip
```
* Reboot to system
