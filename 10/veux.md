### Pre-installation:

* Recovery (from download page, recovery button)
* Optional gapps (from download page, gapps button)

### First time installation (clean flash):

* Backup your data to PC, OTG flash drive
* Boot to fastboot and flash recovery

```
fastboot flash boot boot.img
fastboot flash vendor_boot vendor_boot.img
```

* Boot to Crdroid recovery (volume up + power button)
* Select Apply Update
* Apply Update from ADB
* Connect your phone to PC
* Now sideload crDroid zip

```
adb sideload crDroid.zip
```

* Tap yes on the prompt that comes after sideloading crDroid.zip
* Format data
* Reboot to system

### Flashing gapps:

* After tapping yes on the prompt that came after sideloading crDroid.zip, don't format data or reboot to system
* Sideload gapps.zip

```
adb sideload gapps.zip
```

* Format data
* Reboot to system

### Update installation (dirty flash):
* Boot to Crdroid recovery (volume up + power button)
* Select Apply Update
* Apply Update from ADB
* Connect your phone to PC
* Now sideload crDroid.zip

```
adb sideload crDroid.zip
```

* Tap yes on the prompt that comes after sideloading crDroid.zip
* Reboot to system

* If you had flashed gapps in the previous version then, after tapping yes on the prompt
* Sideload gapps.zip

```
adb sideload gapps.zip
```

* Reboot to system

#### Via OTA:
* Go to Settings -> System -> Updater and download latest build
* Choose install and let it finish
* Reboot
* If you had flashed gapps in the previous version then, after rebooting to system if the gapps crash
* Reboot to crDroid recovery (volume up + power button)
* Sideload gapps.zip

```
adb sideload gapps.zip
```

* Reboot to system


