### Pre-installation:

* **Make Sure to be on V14.0.6.0.TKLINXM**
* Optional gapps (from download page, gapps button)


### First time installation (clean flash):
* reboot to fastboot using
```
adb reboot bootloader
```
* Flash boot image using
```
fastboot flash boot boot.img
```
* Boot to recovery using
```
fastboot reboot recovery
```
* Format data
* Choose Advanced, ADB Sideload
* Now install crDroid zip via sideload and reboot

```
adb sideload crdroid.zip
```
* Go back to main menu and reboot to recovery to install gapps (if you don't want gapps, reboot to system)
* Optional - POCO M5s/Redmi Note 10S indonesia users flash V13.0.5 POCO Firmware
* To install gapps, simply sideload gapps.zip the same way you installed crDroid.zip then reboot to system

### Update installation:
* Boot to recovery
* Choose Advanced, ADB Sideload
* Now install crDroid zip via sideload and reboot
* Make sure to reflash Gapps/Firmware If Required
```
adb sideload crdroid.zip
```
#### Via OTA:
* Go to Settings -> System -> Updater and download latest build
* Choose install and let it finish
* Reboot
