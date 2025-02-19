### Pre-installation:
---

1. Enable developer options for your device by tapping 7 times on *build number* in *About* section of your phone.
2. Enable USB debugging under developer options.
3. Platform tools needs to be installed on your computer.
4. Enable OEM unlock in the Developer options under device Settings, if present.
5. Remove all Google accounts from your device to avoid “Factory reset protection”
6. Backup your device.


### Unlocking the bootloader:

1. Connect the device to your PC via USB.
2. Verify your device is being recognized by computer by opening a command prompt (on Windows) or terminal (on Linux or macOS) window, and type:
```
adb devices
```
You sould see your device listed.
3. Reboot to bootloader by typing:
```
adb -d reboot bootloader
```
You can also boot into fastboot mode via a key combination:

- With the device powered off, hold ***Volume Up*** + ***Volume Down*** + ***Power***.

4. Once the device is in fastboot mode, verify your PC finds it by typing:
```
fastboot devices
```

5. Now type the following command to unlock the bootloader: 
```
fastboot oem unlock
```
Navigate using volume buttons and unlock the bootloader.

6. Reboot your device if it does not get automatically rebooted.
7. Your device will reset completely so you would need to re-enable usb debugging.

### First time installation (clean flash):

**Warning!**
If you are coming from another custom rom, make sure you have the latest firmware (https://github.com/Wishmasterflo/Firmware_flasher?tab=readme-ov-file)

- Download vbmeta, recovery and rom.
- Download gapps (optional).
- Reboot your device into bootloader.
```
adb reboot bootloader
``` 
- Flash the vbmeta and recovery to your device
```
fastboot flash vbmeta vbmeta.img
fastboot flash recovery recovery.img
```
- Use the volume and power buttons to navigate and boot into recovery mode.
- While in recovery, tap factory reset and then wipe data to format the device.
- Now return to main menu and tap on *Apply Update* and then *Apply from ADB* 
- On your computer, install the rom using
```
adb sideload crDroid.zip
```
- After completion, Reboot to recovert again.
- [optional] Install gapps by tapping *Apply Update* and then *Apply from ADB* then *adb sideload gapps.zip*
- Reboot your device.

### Update installation:

#### Via recovery (recommended way):
* Restart your device and boot to recovery
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



