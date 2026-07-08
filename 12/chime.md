### Pre-installation:

* Make sure you have latest firmware available for your country.
* Gapps package (optional) (from download page, gapps button)
* Recovery (from download page, recovery button)
* A pc with platform-tools working (adb/fastboot)


### First time installation (clean flash):

* Unlock Bootloader
* Reboot to bootloader
* Flash the boot image:

```
fastboot flash boot boot.img
```

* Flash the DTBO image:

```
fastboot flash dtbo dtbo.img
```

Flash the recovery image:

```
fastboot flash recovery recovery.img
```

* Reboot to recovery:

```
fastboot reboot recovery
```

* In recovery mode, navigate to **Factory reset -> Format data/factory reset** and confirm to format the device.
* After formatting, return to the main menu and navigate to **Apply update -> Apply from ADB**.
* Sideload the ROM:

```
adb sideload crdroid.zip (replace "crdroid" with actual filename)
```

* Reboot to recovery to sideload any add-ons (e.g., Magisk, GApps, Firmware etc).
* Finally, reboot to the system.

### Update installation:

#### Via recovery (recommended way):

* Boot to recovery
* Choose apply update and Apply from ADB
* Now install crDroid zip via sideload and reboot

```
adb sideload crDroid.zip
```

#### Via OTA:

* Go to Settings -> System -> Updater and download latest build
* Choose install and let it finish
* If having gapps, reboot to recovery and sideload gapps package again
* Reboot
