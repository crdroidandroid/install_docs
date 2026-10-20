### Pre-installation:

* Make sure your bootloader is unlocked.
* Make sure your device is running compatible Motorola stock firmware.
* Stock firmware for bangkk is available on [Lolinet] (https://mirrors.lolinet.com/firmware/lenomola/2023/bangkk/official/). Choose the package matching your device's region and software channel.
* Download the crDroid 13.0 (Android 17) build for your device.
* Download the corresponding crDroidRecovery.zip package.
* Optionally, download compatible Android 17 GApps. crDroid is vanilla.
* Make sure ADB and Fastboot (Android Platform Tools) are installed on your computer.
* Back up your important files before proceeding.

### First time installation (clean flash):

*Warning: A clean installation will erase all user data, including internal storage

1. Download the crDroid ROM and its corresponding crDroidRecovery.zip package.

2. Extract the following images from crDroidRecovery.zip:
   * boot.img
   * dtbo.img
   * vendor_boot.img

3. Reboot your device into bootloader mode.

4. Flash the recovery images using Fastboot:

```
fastboot flash boot boot.img
fastboot flash dtbo dtbo.img
fastboot flash vendor_boot vendor_boot.img
```

5. Reboot into crDroid Recovery using the bootloader menu.

6. In recovery, navigate to:

   *Factory Reset > Format Data/Factory Reset > Agree

7. Return to the recovery main menu and select:

   *Apply Update > Apply from ADB

8. On your computer, sideload the crDroid ROM:

```
adb sideload crDroidAndroid-17.0-20261017-bangkk-v13.0.zip
```

9. Once installation finishes, recovery may ask you to reboot into recovery again. Select *Yes*.

10. For GApps:
    * Select *Apply Update > Apply from ADB* again.
    * Sideload your compatible Android 17 GApps ZIP using **adb sideload** followed by its filename.
    * Do not boot into Android before installing GApps.

11. Once everything is installed, select **Reboot system now**.

12. Wait for the first boot to complete and finish the Android setup.

### Update installation:

*These instructions apply to updates between compatible crDroid 13 builds. Back up your data before updating.**

1. Download the newer crDroid 13 build for bangkk

2. Reboot into crDroid Recovery

3. Select:
   *Apply Update > Appy from ADB

4. Sideload the downloaded crDroid ROM ZIP from your computer
```
adb sideload crDroidAndroid-17.0-[date]-bangkk-v13.0.zip
```

5. If prompted, reboot into recovery again.

6. Reinstall compatible GApps if required by your installation.

7. Select **Reboot system now**.
