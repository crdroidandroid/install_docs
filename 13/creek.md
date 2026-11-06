### Pre-installation:

* Unlock bootloader
* Download the latest crDroid zip
* Download the provided recovery
* Back up all important data before proceeding
* Formatting data will erase internal storage and user data

### First time installation (clean flash):

1. Download the ROM zip and provided recovery
2. Boot the device into the provided recovery
3. Select Install and flash the crDroid zip
4. After flashing is complete, return to the recovery main menu
5. Select Format Data
6. Type **yes** to confirm formatting
7. Wait until formatting is complete
8. Select Reboot System
9. Wait for the first boot to complete

### Update installation (dirty flash):

1. Reboot the device into the provided recovery
2. Select **Apply Update** and then **Apply from ADB**
3. Sideload the crDroid ROM zip:

   `adb sideload crDroid-ROM.zip`
   
4. After flashing is complete, select **Reboot to Recovery**
5. Select **Apply Update** and then **Apply from ADB** again
6. Sideload a compatible GApps package:

   `adb sideload GApps.zip`
7. Reboot to System
8. Wait for the device to boot completely

* Do not format data when performing a dirty flash.
* Use a GApps package compatible with Android 17 and ARM64. Skip the GApps step if you want to keep the Vanilla build without Google Apps.
