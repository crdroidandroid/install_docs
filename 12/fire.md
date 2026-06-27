### Pre-installation:

* Unlocked bootloader.
* Latest Android 14 firmware for Redmi 12 / POCO M6 Pro 4G (fire).
* crDroid recovery from the download page or extracted from the ROM package.
* Optional GApps package from the download page if you want Google apps.
* ADB and fastboot installed on your computer.

### First time installation (clean flash):

* Boot the device to bootloader mode.

```
adb reboot bootloader
```

* Flash crDroid recovery.

```
fastboot flash vendor_boot vendor_boot.img
fastboot reboot recovery
```

* In recovery, choose **Factory reset** > **Format data/factory reset** and confirm.
* Return to the main menu and choose **Apply update** > **Apply from ADB**.
* Sideload the crDroid package.

```
adb sideload crdroid.zip
```

* If you want GApps, reboot back to recovery, choose **Apply update** > **Apply from ADB**, then sideload the GApps package.

```
adb sideload gapps.zip
```

* Reboot to system.

### Update installation:

* Use the built-in updater from **Settings** > **System** > **Updater**, or boot to recovery and sideload the new crDroid package.

```
adb sideload crdroid.zip
```

* If you use GApps and recovery asks you to reflash them after the ROM update, reboot back to recovery and sideload the same or newer GApps package before booting system.
