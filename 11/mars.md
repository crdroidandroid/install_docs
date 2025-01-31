# Installing crDroid 11 on Your Device

**Warning:** The provided instructions are for crDroid 11. These will only work if you follow every section and step precisely. **Do not continue after something fails!**

## Basic requirements
1. **Read through the instructions at least once before actually following them**, so as to avoid any problems due to any missed steps!
2. **Make sure your computer has adb and fastboot**. Setup instructions can be found [here](https://wiki.lineageos.org/adb_fastboot_guide).
3. **Enable USB debugging on your device**.
4. **Make sure that your model number is one of the following** (exact match required!):
   - M2102K1AC
5. **Boot your device with the stock OS at least once and check every functionality.**

> **Warning:** Make sure that you can send and receive SMS and place and receive calls (also via WiFi and LTE, if available), otherwise it won’t work on crDroid either! Additionally, some devices require that VoLTE/VoWiFi be utilized once on stock to provision IMS.
6. **Remove all Google accounts from your device to avoid “Factory reset protection”**.
7. **crDroid is provided as-is with no warranty. While we attempt to verify everything works you are installing this at your own risk!**

> **Warning:** Before following these instructions please ensure that the device is currently using Android 14 firmware. If the vendor provided multiple updates for that version, e.g. security updates, make sure you are on the latest! If your current installation is newer or older than Android 14, please upgrade or downgrade to the required version before proceeding (guides can be found on the internet!).

## Flashing additional partitions
> **Warning:** This platform requires additional partitions to be flashed for recovery to work properly, the process to do so is described below.

1. Download the following files from [here](https://crdroid.net/mars/11):
   - **dtbo.img**
   - **vendor_boot.img**
2. **Power off the device, and boot it into bootloader mode:**
   - With the device powered off, hold Volume Down + Power. Keep holding both buttons until the word “FASTBOOT” appears on the screen, then release.
3. **Flash the downloaded image files to your device by typing:**

```
fastboot flash dtbo dtbo.img
fastboot flash vendor_boot vendor_boot.img
```

## Installing crDroid Recovery using fastboot
1. **Download crDroid Recovery**. Simply download the latest recovery file, named **boot.img**.
> **Important:** Other recoveries may not work for installation or updates. We strongly recommend to use the one linked above!
2. **Flash recovery onto your device:**

```
fastboot flash boot boot.img
```
3. **Now reboot into recovery to verify the installation. Do not reboot into the existing OS, since it will overwrite the recovery you just installed!**
   - With the device powered off, hold Volume Up + Power. Keep holding both buttons until the “MI” logo appears on the screen, then release.

> **Note:** If you can’t power down the device, try long-pressing the key-combination (if any was used in the instructions above) until the device reboots and follow the instructions above.
>
> **Note:** If your recovery does not show the Crdroid logo, you accidentally booted into the wrong recovery. Please start at the top of this section!

## Installing crDroid from recovery
1. **Download the crDroid zip file that you would like to install or build the package yourself.**
2. If you are not in recovery, **reboot into recovery:**
   - With the device powered off, hold Volume Up + Power. Keep holding both buttons until the “MI” logo appears on the screen, then release.
3. **Now tap Factory Reset, then Format data / factory reset and continue with the formatting process.** This will remove encryption and delete all files stored in the internal storage, as well as format your cache partition (if you have one).
4. **Return to the main menu**.
5. **Sideload the crDroid .zip package but do not reboot before you read/followed the rest of the instructions!**
   - On the device, select “Apply Update”, then “Apply from ADB” to begin sideload.
   - On the host machine, sideload the package using:
   
```
adb -d sideload filename.zip
```

> **Tip:** After the package is installed, recovery will inform you that reboot to recovery is required to install add-ons. In case you want to do that, please select “Yes,” otherwise “No”.
>
> **Tip:** Normally, adb will report **Total xfer: 1.00x**, but in some cases, even if the process succeeds the output will stop at 47% and report **adb: failed to read command: Success**. In some cases it will report **adb: failed to read command: No error** or **adb: failed to read command: Undefined error: 0** which is also fine.

## Installing Add-Ons
> **Note:** If you don’t want to install any add-on (such as Google Apps), you can skip this whole section!
>
> **Warning:** If you want to install Google Apps add-on package (use the arm64 architecture), you can download it from [here - gapps button](https://crdroid.net/mars/11). This add-on needs to be installed before booting into crDroid for the first time!
1. Click Apply Update, then Apply from ADB, then:

```
adb -d sideload filename.zip
```
   for all desired packages in sequence.
3. When presented with a screen that says **Signature verification failed**, click **Yes**. It is expected as add-ons aren’t signed with LineageOS’s official keys.
