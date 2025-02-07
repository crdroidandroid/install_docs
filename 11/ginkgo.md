---

[Read before installation)](#title1)  
[Prepare everything before installation](#title2)  
[First time installation (Clean Flash)](#title3)  
[Update to a newer build of the same crDroid version](#title4)  

---

# <a id="title1">Read before installation:</a>

1. Read through the instructions at least once before actually following them, so as to avoid any problems due to any missed steps!
2. Make sure your computer has ***adb*** and ***fastboot***.
3. Enable USB debugging on your device.
4. crDroid is provided as-is with no warranty. You are installing this at your own risk!
--- 

# <a id="title2">Prepare everything before installation:</a>

1. Download Recovery from download page
2. Download Firmware for your device
    - ginkgo: [Download](https://sourceforge.net/projects/shawkteam/files/ginkgo/addons/fw_ginkgo_miui_GINKGOGlobal_V12_5_2_0_RCOMIXM_75abe1782e_11_0.zip/download)
    - willow: [Download](https://sourceforge.net/projects/shawkteam/files/ginkgo/addons/fw_willow_miui_WILLOWGlobal_V12.5.6.0.RCXMIXM_b9c4b22e3f.zip/download)
3. This ROM Uses Dynamic Partitioning system, so you should use Dynamic Partition Converter
    - Dynamic Partition Converter: [Download](https://sourceforge.net/projects/kycii91-j4plus/files/Ginkgo/Ginkgo_Retrofit_Dynamic_Partitions_Converter.zip/download)

--- 

# <a id="title3">First time installation (Clean Flash)</a>

* NOTE: If you are comming from Stock ROM or another Custom ROM you should follow this instructions

1. Connect your phone to PC and enter to fastboot mode 
- With the device powered off, hold ***Volume Down*** + ***Power**
2. On the computer, open a command prompt (on Windows) or terminal (on Linux or macOS)
3. Once the device is in fastboot mode, verify your PC finds it by typing:

```
fastboot devices
```
If you don’t get any output or an error:

- on Windows: make sure the device appears in the device manager without a triangle. Try other drivers until the command above works!
- on Linux or macOS: If you see ***no permissions fastboot*** try running ***fastboot*** as root. When the output is empty, check your USB cable and port!

4. Now type the following command for flashing recovery:

```
fastboot flash recovery recovery.img
```

5. Reboot to recovery 
- With the device powered off, hold ***Volume UP*** + ***Power**
6. Now wipe
    - System
    - Vendor
    - Data
    - Dalvik 
    - Cache
    - Metadata
7. Untick Unmount System before installing a ZIP in Settings
8. Flash given Dynamic Partition Converter
- via SD Card or OTG, go to files >> dynamicconverter.zip
- via ADB Sideload:

```
adb sideload dynamicconverter.zip
```

9. Now Flash the given firmware for your device
- via SD card or OTG, go to files >> firmwareforyourdevice.zip
- via ADB Sideload: 

```
adb sideload firmwareforyourdevice.zip
```

10. Finally, Now Flash the ROM.Zip
- via SD card or OTG, go to files >> Flash crDroidAndroid-15.0-XXXXXXXX-ginkgo-V11.X.zip
- via ADB Sideload:

```
adb sideload crDroidAndroid-15.0-XXXXXXXX-ginkgo-V11.X.zip
```

**Tip** 
Skip this step if you don't want Google Apps (GApps)

11. Flash get Google Apps (GApps):
- via SD card or OTG, go to files >> GApps.zip
- via ADB Sideload:

```
adb sideload GApps.zip
```

12. Format data 
13. Reboot to the System (Ignore No OS Installed warning)
14. Done

----

# <a id="title4">Update to a newer build of the same crDroid version</a>

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
    - With the device powered off, hold ***Volume UP*** + ***Power***.
3. Flash the crDroid.zip package but **do not reboot** before you read/followed the rest of the instructions!
 - via SD card or OTG, go to files >> Flash crDroidAndroid-15.0-XXXXXXXX-ginkgo-V11.X.zip
 - via ADB Sideload:

```
adb sideload crDroidAndroid-15.0-XXXXXXXX-ginkgo-V11.X.zip
```

**Tip**
Skip this step if you are not using Google Apps (GApps)

4. Flash GApps
- via SD card or OTG, go to files >> GApps.zip
- via ADB Sideload:

```
adb sideload GApps.zip
```

5. Reboot to the the system
6. Done.

---