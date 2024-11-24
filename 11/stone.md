### Pre-installation:

* Unlocked bootloader
* Latest regional HyperOS firmware installed
* Recovery (from download page, recovery button)
* Optional gapps (from download page, gapps button)

### First time installation (clean flash):

* Backup your data to PC, OTG flash drive
* Boot to fastboot and flash recovery (volume down + power button)

```
fastboot flash boot boot.img
```

* Boot to crDroid recovery (volume up + power button)
* Format Data
* Sideload crDroid zip

```
adb sideload crDroid.zip
```

### Install gapps (optional)
* Reboot to recovery
* Sideload gapps.zip

```
adb sideload gapps.zip
```

* Reboot to system

### Update installation:
#### Via OTA:

* Go to Settings -> System -> Updater and download latest build
* Choose install and let it finish
* Reboot
