### Pre-installation
* **Mi Note 3 12.0.1.0 or later fw is required**
* Download ROM's zip (crdroid.zip)
* Download Recovery image (recovery.img)
* Optionally download Gapps package

## First Time installation

* Reboot phone to bootloader mode (adb reboot bootloader)
* Install recovery image

```
fastboot flash recovery recovery.img
```
* Reboot to recovery 
* If FW version is lower than 12.0.1.0 install via adb sideload

```
adb sideload firmware.zip
```
* Wipe data / Factory reset
* Install ROM Package via adb sideload

```
adb sideload crdroid.zip
```
* Optionally install Gapps package via adb sideload

```
adb sideload gapps.zip
```

### Dirty flash installation
* Reboot phone to recovery mode
* Install ROM via adb sideload

```
adb sideload crdroid.zip
```
* Optionally install Gapps package via adb sideload

```
adb sideload gapps.zip
```

# Via OTA
* Go to Settings -> System -> Updater and download latest build
* Choose install and let it finish
* Reboot
