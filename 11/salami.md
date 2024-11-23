### Pre-installation
* Download the latest ROM file (referred to as **`crdroid.zip`**).
* Download support files from the site:
  - **boot.img**
  - **dtbo.img**
  - **vbmeta.img**
  - **vendor_boot.img**
  - **recovery.img**
* Download the latest GApps (referred to as **`gapps.zip`**).

*(Files may have YYYYMMDD date in file name, download latest files in that case)*

---

### Step 1: Unlock Bootloader
**This step can be skipped if bootloader is already unlocked.**

1. Enable **OEM unlock** in the Developer options under device Settings, if present.

2. Connect the device to your PC via USB.

3. On the computer, open a command prompt (on Windows) or terminal (on Linux or macOS) window, and type:

```
adb -d reboot bootloader
```
*(You can also power off the device, and boot it into bootloader mode by holding **Volume Up + Volume Down + Power**)*

4. Once the device is in fastboot mode, verify your PC finds it by typing:

```
fastboot devices
```

5. Now type the following command to unlock the bootloader:

```
fastboot flashing unlock
```
  - If the device doesn’t automatically reboot, reboot it. It should now be unlocked.
  - Since the device resets completely, you will need to **re-enable USB debugging** to continue.

### Step 2: Flash Additional Partitions and Recovery 
**This step can be skipped if you have compatible custom recovery.**

1. Download and keep support files (mentioned in pre-installation) ready.

2. On the computer, open a command prompt (on Windows) or terminal (on Linux or macOS) window, and type:

```
adb -d reboot bootloader
```
*(You can also power off the device, and boot it into bootloader mode by holding **Volume Up + Volume Down + Power**)*

3. Flash the downloaded image files to your device by typing:

```
fastboot flash boot boot.img
fastboot flash dtbo dtbo.img
fastboot flash vbmeta vbmeta.img
fastboot flash vendor_boot vendor_boot.img
fastboot flash recovery recovery.img
```

*(If support files have YYYYMMDD date prefix, rename respective img file accordingly)*

4. Now use the **Volume Keys** to navigate to and to select the **Recovery** option with **Power Key**.


### Step 3: Flash ROM and Gapps
**This step can be also used for update installation**

1. Ensure you have downloaded latest crdroid.zip package from the link above

2. If you are not in recovery, reboot into recovery:
  - With the device powered off, hold **Volume Down + Power**

3. For clean / first-time installation - Tap **Factory Reset** > **Format data** and continue with the formatting process. This will remove encryption and delete all files stored in the internal storage, as well as format your cache partition (if you have one). This step can be skipped for update installation.

4. Return to the main menu.

5. Sideload the crdroid.zip package but do not rebootbefore you read/followed the rest of the instructions!
  - On the device, tap **Apply Update** > **Apply from ADB** to begin sideload.
  - On the host machine, sideload the package using:

```
adb -d sideload filename.zip
```

6. After installing ROM package, recovery will ask reboot in recovery again for installing additional packages, reboot in recovery and
  - On the device, tap **Apply Update** > **Apply from ADB** to begin sideload.
  - On the host machine, sideload the package using:

```
adb -d sideload gapps.zip
```

---

### Update Installation
* If you're updating to a newer version, you can either:
  - **Via OTA**: Use the in-built **Updater**. (Settings > System > Update)
  - **Via Recovery**: Follow **Step 3** above **without factory reset**.

*(No need to flash GApps again if updating via OTA)*

