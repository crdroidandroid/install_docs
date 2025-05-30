### Pre-installation:

* **Remember, everything you do is your responsibility. I am not responsible for bricked devices.**
* Optional gapps (from download page, gapps button)


### First time installation (clean flash):
* Boot to recovery
* Wipe: dalvik cache, cache, system, vendor, data
* Go to Install -> Select crdroid.zip -> Flash
* or if you want use ADB Sideload:
```
adb sideload crdroid.zip
```
* Go back to main menu and reboot to recovery to install gapps (if you don't want gapps, reboot to system)
* To install gapps, simply sideload gapps.zip or flash via sdcard the same way you installed crdroid.zip then reboot to system
* Format Data
* Reboot to System 
### Update installation:
* Boot to recovery
* Go to Install -> Select crdroid.zip -> Flash
* or if you want use ADB Sideload:
```
adb sideload crdroid.zip
```
* Reboot to System
#### Via OTA:
* Go to Settings -> System -> Updater and download latest build
* Choose install and let it finish
* Reboot
