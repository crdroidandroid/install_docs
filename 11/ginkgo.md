---

[Read before installation](#title1)  
[Prepare everything before installation](#title2)  
[First time installation (Clean Flash)](#title3)  
[Update to a newer build of the same crDroid version](#title4)  
[Troubleshot](#title5) 

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

## If you are coming from Non - Dynamic ROM

1. Reboot to recovery 
- With the device powered off, hold ***Volume UP*** + ***Power**
2. Now wipe
    - System
    - Vendor
    - Data
    - Dalvik 
    - Cache
    - Metadata
3. Install given recovery on Download page
- via SD card or OTG, go to files >> select recovery.img >> flash to recovery
4. After flashing given recovery reboot to your new recovery
5. Untick **Unmount System before installing** a ZIP in Settings
6. Flash Retrofit Dynamic Partition Converter
- via SD Card or OTG, go to files >> dynamicconverter.zip
- via ADB Sideload:

```
adb sideload dynamicconverter.zip
```

7. Flash Firmware
- via SD card or OTG, go to files >> firmwareforyourdevice.zip
- via ADB Sideload: 

```
adb sideload firmwareforyourdevice.zip
```

8. Finally, Now Flash the ROM.Zip
- via SD card or OTG, go to files >> Flash crDroidAndroid-15.0-XXXXXXXX-ginkgo-V11.X.zip
- via ADB Sideload:

```
adb sideload crDroidAndroid-15.0-XXXXXXXX-ginkgo-V11.X.zip
```

**Tip** 
Skip this step if you don't want Google Apps (GApps)

9. Flash if you get Google Apps (GApps):
- via SD card or OTG, go to files >> GApps.zip
- via ADB Sideload:

```
adb sideload GApps.zip
```

10. Format data 
11. Reboot to the System (Ignore No OS Installed warning)
12. Voila
---

## If you are coming from another dynamic ROM

1. Reboot to Recovery
2. Wipe
    - System
    - Vendor
    - Data
    - Dalvik 
    - Cache
    - Metadata
3. Finally, Now Flash the ROM.Zip
- via SD card or OTG, go to files >> Flash crDroidAndroid-15.0-XXXXXXXX-ginkgo-V11.X.zip
- via ADB Sideload:

```
adb sideload crDroidAndroid-15.0-XXXXXXXX-ginkgo-V11.X.zip
```

**Tip** 
Skip this step if you don't want Google Apps (GApps)

4. Flash get Google Apps (GApps):
- via SD card or OTG, go to files >> GApps.zip
- via ADB Sideload:

```
adb sideload GApps.zip
```

5. Voila!
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
---

## Via recovery:

1. Reboot to Recovery 
2. Flash the update zip
- via SD card or OTG, go to files >> Flash crDroidAndroid-15.0-XXXXXXXX-ginkgo-V11.X.zip
- via ADB Sideload:

```
adb sideload crDroidAndroid-15.0-XXXXXXXX-ginkgo-V11.X.zip
```

3. Reboot System
4. Voila
---

# <a id="title5">Troubleshot</a>

1. Wifi/Bluetooh is not working

Q: Why am I having this problem?
A: This is a problem with the kernel module, wifi and bluetooth module cannot be loaded after the first boot of the rom.S*ome users experience this problem while others do not, which is a strange situation.

*Solution:
1.Shut down phone
2.Turn on phone

**Notes**
- Do not reboot, apply this way
- If you have another problems or do you want report any bug, get support click 'support' section on Donwload page!

---
