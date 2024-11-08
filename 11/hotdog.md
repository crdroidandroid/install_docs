---

[First time installation (clean flash)](#title1)  
[Update to a newer build of the same crDroid version](#title2)  
[Upgrade to a higher version of crDroid (e.g. crDroid 10 -> crDroid 11) - Not recommended](#title3)  

---
# <a id="title1">First time installation (clean flash):</a>

## Basic requirements
1. Read through the instructions at least once before actually following them, so as to avoid any problems due to any missed steps!
2. Make sure your computer has ***adb*** and ***fastboot***.
3. Enable USB debugging on your device.
4. Make sure that your model is actually listed in the Supported models:
    - HD1910
    - HD1911
    - HD1913
    - HD1917
5. Boot your device with the stock OS at least once and check every functionality.

**Warning!**  
Make sure that you can send and receive SMS and place and receive calls (also via WiFi and LTE, if available), otherwise it won’t work on crDroid either! Additionally, some devices require that VoLTE/VoWiFi be utilized once on stock to provision IMS.

---

6. crDroid is provided as-is with no warranty. You are installing this at your own risk!

**Warning!**  
Before following these instructions please ensure that the device is currently using Android 12 firmware.
If the vendor provided multiple updates for that version, e.g. security updates, make sure you are on the latest!
If your current installation is older Android 12, please upgrade to the required version before proceeding (guides can be found on the internet!).

---

## Checking the correct firmware
Installation on your device requires a specific firmware version to be installed before you continue.

- Firmware refers to a device-specific set of images that are included in, and updated by the stock OS
- crDroid builds for this device require an Android 12 version of the stock OS to be installed prior to following the installation guide
- Please ensure that you are checking the Android version, and not the vendor OS version
- Being on another custom ROM, including unofficial builds of the same version of crDroid, does not ensure that this requirement has been fulfilled
- Please re-read this section as many times as necessary to fully understand the requirements

**Note**  
If you are unsure what firmware version you are currently on, we strongly recommend returning to the corresponding stock OS before following the installation guide!

---

Failing to install the correct firmware version prior to installation may result in failure to install crDroid, unexpected crashes post-installation, or permanent damage to your device!

## Unlocking the bootloader:

**Note**  
The steps below only need to be run once per device.

---

**Warning!**  
Unlocking the bootloader will erase all data on your device! Before proceeding, ensure the data you would like to retain is backed up to your PC and/or your Google account, or equivalent. Please note that OEM backup solutions like OnePlus, Samsung, Motorola backup may not be accessible from crDroid once installed.

---

1. Enable OEM unlock in the Developer options under device Settings, if present.
2. Connect the device to your PC via USB.
3. On the computer, open a command prompt (on Windows) or terminal (on Linux or macOS) window, and type:

```
adb reboot bootloader
```
You can also boot into fastboot mode via a key combination:

- With the device powered off, hold ***Volume Up*** + ***Volume Down*** + ***Power***.

4. Once the device is in fastboot mode, verify your PC finds it by typing:

```
fastboot devices
```
If you don’t get any output or an error:

- on Windows: make sure the device appears in the device manager without a triangle. Try other drivers until the command above works!
- on Linux or macOS: If you see ***no permissions fastboot*** try running ***fastboot*** as root. When the output is empty, check your USB cable and port!

5. Now type the following command to unlock the bootloader:

```
fastboot oem unlock
```
  
**Note**  
At this point, the device may display on-screen prompts which will require interaction to continue the process of unlocking the bootloader. Please take whatever actions the device asks you to in order to proceed.

---

6. If the device doesn’t automatically reboot, reboot it. It should now be unlocked.
7. Since the device resets completely, you will need to re-enable USB debugging to continue.

## Flashing additional partitions

**Warning!**  
This platform requires additional partitions to be flashed for recovery to work properly, the process to do so is described below.

---

1. Download the latest versions of the following files from download page, recovery button.
    - crDroidAndroid-15.0-YYYYMMDD-v11.X-***dtbo.img***
    - crDroidAndroid-15.0-YYYYMMDD-v11.X-***vbmeta.img***
2. Power off the device, and boot it into bootloader mode:
    - With the device powered off, hold ***Volume Up*** + ***Volume Down*** + ***Power***.
3. Flash the downloaded image files to your device by typing:

```
fastboot flash dtbo crDroidAndroid-15.0-YYYYMMDD-v11.X-dtbo.img
fastboot flash vbmeta crDroidAndroid-15.0-YYYYMMDD-v11.X-vbmeta.img
```

## Installing crDroid Recovery using ***fastboot***

1. Download **crDroid Recovery** (see download page, recovery button). Simply download the latest recovery file, named ***crDroidAndroid-15.0-YYYYMMDD-v11.X-recovery.img***.

**Important**  
Other recoveries may not work for installation or updates. We strongly recommend to use the one linked above!

---

2. Flash recovery onto your device:

```
fastboot flash recovery crDroidAndroid-15.0-YYYYMMDD-v11.X-recovery.img
```
Now reboot into recovery.

- Use the menu to navigate to and to select the Recovery option.

## Installing crDroid from recovery
1. Download the latest crDroid zip file.
2. If you are not in recovery, reboot into recovery:
    - With the device powered off, hold ***Volume Down*** + ***Power***.
3. Now tap ***Factory Reset***, then ***Format data / factory reset*** and continue with the formatting process. This will remove encryption and delete all files stored in the internal storage, as well as format your cache partition (if you have one).
4. Return to the main menu.
5. Sideload the crDroid.zip package but **do not reboot** before you read/followed the rest of the instructions!
    - On the device, select ***Apply Update***, then ***Apply from ADB*** to begin sideload.
    - On the host machine, sideload the package using:

```
adb sideload crDroid_zip_file.zip
```
  
**Tip**  
After the package is installed, recovery will inform you that reboot to recovery is required to install add-ons (for example: GoogleApps). In case you want to do that, please select “Yes,” otherwise “No”.

---

**Tip**  
Normally, adb will report **Total xfer: 1.00x**, but in some cases, even if the process succeeds the output will stop at 47% and report **adb: failed to read command: Success**. In some cases it will report **adb: failed to read command: No error** or **adb: failed to read command: Undefined error: 0** which is also fine.

---

## Installing Add-Ons
**Note**  
If you don’t want to install any add-on (such as Google Apps), you can skip this whole section!

---

**Warning!**  
If you want to install Google Apps add-on package, you can download it from download page, gapps button. This add-on needs to be installed **before** booting into crDroid for the first time!

---

1. Click ***Apply Update***, then ***Apply from ADB***, then ***adb sideload <addon_filename>.zip*** for all desired packages in sequence.

## All set!
Once you have installed everything successfully, you can now reboot your device into the OS for the first time!

- Click the back arrow in the top left of the screen, then ***Reboot system now***.

**Note**  
The first boot usually takes no longer than 15 minutes, depending on the device. If it takes longer, you may have missed a step, otherwise feel free to get assistance.

---

# <a id="title2">Update to a newer build of the same crDroid version</a>

## Using the crDroid Updater app

**Note**  
crDroid strongly recommends using our builtin Updater app. Alternative methods are supported, however.

---

1. Open Settings, navigate to ***System***, then ***Updater***.
2. Click the Refresh Icon in the top right corner.
3. Choose which update you’d like and press ***Download***.
4. When the download completes, click ***Install***. Once the update process has finished, the device will display a ***Reboot*** button, you may need to go into the Updater menu in Settings, ***System*** to see it. This will reboot you into the updated system.

## Via recovery:
1. Download the latest crDroid zip file from download page.
    - If the Google Apps add-on has been installed, then check for a new version (download page, gapps button).
2. If you are not in recovery, reboot into recovery:
    - With the device powered off, hold ***Volume Down*** + ***Power***.
3. Sideload the crDroid.zip package but **do not reboot** before you read/followed the rest of the instructions!
    - On the device, select ***Apply Update***, then ***Apply from ADB*** to begin sideload.
    - On the host machine, sideload the package using:

```
adb sideload crDroid_zip_file.zip
```
  
**Tip**  
After the package is installed, recovery will inform you that reboot to recovery is required to install add-ons (for example: GoogleApps). In case you want to do that, please select “Yes,” otherwise “No”.

---

**Tip**  
Normally, adb will report **Total xfer: 1.00x**, but in some cases, even if the process succeeds the output will stop at 47% and report **adb: failed to read command: Success**. In some cases it will report **adb: failed to read command: No error** or **adb: failed to read command: Undefined error: 0** which is also fine.

---

## Installing Add-Ons
**Note**  
If you don’t want to install any add-on (such as Google Apps), you can skip this whole section!

---

**Warning!**  
If you want to install Google Apps add-on package, you can get on download page, gapps button. This add-on needs to be installed **before** booting into crDroid for the first time!

---

1. Click ***Apply Update***, then ***Apply from ADB***, then ***adb sideload <addon_filename>.zip*** for all desired packages in sequence.

## All set!
Once you have installed everything successfully, you can now reboot your device into the OS!

- Click the back arrow in the top left of the screen, then ***Reboot system now***.

---


# <a id="title3">Upgrade to a higher version of crDroid (e.g. crDroid 10 -> crDroid 11) - Not recommended</a>

## Basic requirements

1. Read through the instructions at least once before actually following them, so as to avoid any problems due to any missed steps!
2. You actually want to upgrade your device to the newest version - if you wish to downgrade to an earlier version of crDroid, follow your device’s instructions for installing crDroid the first time.

## Manually upgrading crDroid

**Note** 
Following these instructions will not wipe your data. It is, however, recommended to save important data before doing so, anyway!

---

**Warning!**  
We recommend doing a "clean install" of the new version. If you decide to upgrade, be prepared for the fact that there may be any additional problems after booting the new system.

---

The updater app does not support upgrades from one version of crDroid to another, and will block installation to any update for a different version. Upgrading manually requires similar steps to installing crDroid for the first time.

1. Download the latest version of ***recovery*** image from download page, recovery button.
2. Download the latest crDroid package.
3. If you are currently using (or now want to use) an application package add-on such as Google Apps, you have the following options:
    - keep using them (download new recovery from download page, recovery button) in order to get the appropriate version.
    - remove them: You can only do so by performing a factory reset, which will also remove all your data.
    - start using them: You can only do so by performing a factory reset, which will also remove all your data. crDroid package the appropriate version now.
4. Make sure your computer has working adb.
5. Enable USB debugging on your device.
6. **Important!** Remove encryption on the device (fingerprints/face/passwords/graphic keys/PIN/etc..) and set ***Screen lock*** to ***None***.
7. Power off the device, and boot it into bootloader mode:
    - With the device powered off, hold ***Volume Up*** + ***Volume Down*** + ***Power***.
8. Flash recovery onto your device:

```
fastboot flash recovery crDroidAndroid-15.0-YYYYMMDD-v11.X-recovery.img
```
Now reboot into recovery.
- Use the menu to navigate to and to select the Recovery option.

5. Sideload the crDroid .zip package but **do not reboot** before you read/followed the rest of the instructions!
    - On the device, select ***Apply Update***, then ***Apply from ADB*** to begin sideload.
    - On the host machine, sideload the package using:

```
adb sideload crDroid_zip_file.zip
```

**Tip**  
After the package is installed, recovery will inform you that reboot to recovery is required to install add-ons (for example: GoogleApps). In case you want to do that, please select “Yes,” otherwise “No”.

---

**Tip**  
Normally, adb will report **Total xfer: 1.00x**, but in some cases, even if the process succeeds the output will stop at 47% and report **adb: failed to read command: Success**. In some cases it will report **adb: failed to read command: No error** or **adb: failed to read command: Undefined error: 0** which is also fine.

---

## Installing Add-Ons
**Note**  
If you don’t want to install any add-on (such as Google Apps), you can skip this whole section!

---

**Warning!**  
If you want to install Google Apps add-on package, you can get on download page, gapps button. This add-on needs to be installed **before** booting into crDroid for the first time!

---

1. Click ***Apply Update***, then ***Apply from ADB***, then ***adb sideload <addon_filename>.zip*** for all desired packages in sequence.

## All set!
Once you have installed everything successfully, you can now reboot your device into the OS!

---
