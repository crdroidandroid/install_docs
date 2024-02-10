### Pre-installation:

* **Latest MIUI Stable based on Android 11**
* Optional gapps (from download page, gapps button)


### First time installation (clean flash):
* Boot to recovery
* Format data
* Choose Advanced, ADB Sideload
* Now install crDroid zip via sideload and reboot

```
adb sideload crdroid.zip
```
* Go back to main menu and reboot to recovery to install gapps (if you don't want gapps, reboot to system)
* To install gapps, simply sideload gapps.zip the same way you installed crDroid.zip then reboot to system

### Update installation:
* Boot to recovery
* Choose Advanced, ADB Sideload
* Now install crDroid zip via sideload and reboot

```
adb sideload crdroid.zip
```
#### Via OTA:
* Go to Settings -> System -> Updater and download latest build
* Choose install and let it finish
* Reboot