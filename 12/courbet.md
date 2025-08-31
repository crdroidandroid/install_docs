### Pre-installation:

* Make sure you have latest firmware available for your country (from download page, firmware button).
* Gapps package (optional) (from download page, gapps button)
* Recovery (from download page, recovery button)
* A pc with platform-tools working (adb/fastboot)
* Optional latest KernelSU-Next manager apk to enable per-app root access (get it on [release page](https://github.com/KernelSU-Next/KernelSU-Next/releases) from GitHub)

### First time installation (clean flash):

* Flash recovery with the custom recovery you already have and reboot to it
* Format data (typing "yes" to remove everything included encryption)
* Enable sideloading in recovery settings
* Sideload crdroid.zip

```
adb sideload path/to/crdroid.zip
```
* Optionally sideload gapps.zip

```
adb sideload path/to/gapps.zip
```
* Reboot system and enjoy crDroid!!

### Update installation (by device itself):

* Download updated crDroid package
* Download updated gapps package if you had them
* Reboot recovery
* Flash crdroid.zip
* Flash gapps.zip if you had them
* Wipe Dalvik/art cache and /cache
* Reboot system

### Update installation (by pc)

* Download updated crDroid package
* Download updated gapps package if you had them
* Reboot recovery
* Activate sideload
* Sideload crdroid.zip

```
adb sideload path/to/crdroid.zip
```
* if you had gapps, re-enable sideload and sideload gapps.zip

```
adb sideload path/to/gapps.zip
```
* Wipe Dalvik/art cache and /cache
* Reboot system and enjoy your updated crDroid!!

* Don't forget to download latest KernelSU-Next manager app to enable per-app root access!
