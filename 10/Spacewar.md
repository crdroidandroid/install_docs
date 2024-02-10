### Pre-installation:

* **NOS stable based on Android 13 firmware is required**
* Optional gapps (from download page, gapps button)


### First time installation (clean flash):
* Boot to recovery
* Format data
* Choose apply update and Apply from ADB
* Now install crDroid zip via sideload and reboot

```
adb sideload crDroid.zip
```
* Go back to main menu and reboot to recovery to install gapps (if you don't want gapps, reboot to system)
* To install gapps, simply sideload gapps.zip the same way you installed crDroid.zip then reboot to system

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