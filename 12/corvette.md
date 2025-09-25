### Pre-installation:

* **ColorOS 15 is required**
* A pc with platform-tools working (adb/fastboot)
* [Link](https://pixeldrain.com/u/hzRTmvwE) to download super_empty.img 

### First time installation (clean flash):

* Extract these images from payload.bin

```
boot init_boot vendor_boot recovery
```

* Reboot to bootloader
* Flash the vendor_boot image:

```
fastboot flash vendor_boot vendor_boot.img
```
* Flash the init_boot image:

```
fastboot flash init_boot init_boot.img
```
* Flash the boot image:

```
fastboot flash boot boot.img
```
* Flash the recovery image:

```
fastboot flash recovery recovery.img
```
* Press the volume key and power key to enter recovery
* In recovery mode, navigate to **Factory reset -> Format data/factory reset** and confirm to format the device.
* After formatting, return to the main menu and navigate to **Apply update -> Apply from ADB**.
* Sideload the ROM:

```
adb sideload crDroid.zip
```
* Go back to main menu and reboot to system

### Possible situations of first time installation
#### Error 7 in first time installation
If you got **Error applying update: 7(ErrorCode::kInstallDeviceOpenError)**, you can follow these steps
* Reboot to bootloader
* Flash super_empty

```
fastboot wipe-super super_empty.img
```
* Press the volume key and power key to enter recovery
* In recovery mode, navigate to **Apply update -> Apply from ADB**.
* Sideload the ROM:

```
adb sideload crDroid.zip
```
* Reboot to Recovery mode and sideload the ROM again
* In recovery mode, navigate to **Factory reset -> Format data/factory reset** and confirm to format the device.
* Reboot and Enjoy

### Update installation:
#### Via recovery (recommended):
* Reboot to recovery
* Choose apply update and Apply from ADB
* Now install crDroid zip via sideload and reboot

```
adb sideload crDroid.zip
```
* Reboot

#### Via OTA:
* Go to Settings -> System -> Updater and download latest build
* Choose install and let it finish
* Reboot
