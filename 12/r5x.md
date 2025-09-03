### Pre-installation
* Download the latest ROM file (referred to as **crdroid.zip**).
* Download support files from the site:
  - **recovery.img**
* Download the latest GApps (referred to as **gapps.zip**).
* Ensure you are on realmeUI 1.0 firmware.
* Make sure your bootloader is already unlocked.

*(Files may have YYYYMMDD date in file name, download latest files in that case)*

---

### Step 1: Flash Recovery 
**This step can be skipped if you have compatible custom recovery.**

1. Download and keep support files (mentioned in pre-installation) ready.

2. On the computer, open a command prompt (on Windows) or terminal (on Linux or macOS) window, and type:

```
adb reboot bootloader
```

3. Once the device is in fastboot mode, verify your PC finds it by typing:

```
fastboot devices
```

4. Flash the downloaded image files to your device by typing:

```
fastboot flash recovery recovery.img
```

*(If support files have YYYYMMDD date prefix, rename respective img file accordingly)*

5. Now reboot into recovery to verify the installation. Do **not** reboot into the existing OS, since it will overwrite the recovery you just installed!

```
fastboot reboot recovery
```

*Note: If your recovery does not show the crDroid logo, you accidentally booted into the wrong recovery. Please start at the top of this section!*

### Step 2: Flash ROM and Gapps
**This step can be also used for update installation**

1. Ensure you have downloaded latest crdroid.zip package from the link above

2. If you are not in recovery, reboot into recovery.

3. For clean / first-time installation - Tap **Factory Reset** > **Format data** and continue with the formatting process. This will remove encryption and delete all files stored in the internal storage, as well as format your cache partition (if you have one). This step can be skipped for update installation.

4. Return to the main menu.

5. Sideload the crdroid.zip package but do not reboot before you read/followed the rest of the instructions!
  - On the device, tap **Apply Update** > **Apply from ADB** to begin sideload.
  - On the host machine, sideload the package using:

```
adb sideload crdroid.zip
```

6. After installing ROM package, you can optionally flash gapps package. This step can be skipped for update installation.
  - On the device, tap **Apply Update** > **Apply from ADB** to begin sideload.
  - On the host machine, sideload the package using:

```
adb sideload gapps.zip
```
---

### Update Installation
* If you're updating to a newer version, you can either:
  - **Via OTA**: Use the in-built **Updater**. (Settings > System > Update)
  - **Via Recovery**: Follow **Step 2** above **without factory reset**.

*(No need to flash GApps again unless newer version of gapps is available)*
