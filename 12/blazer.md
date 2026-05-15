# WARNING: Please follow the below steps for installing v12.10 if not already running stock May SPL due to ABL ARB increments
### Do not OTA update this update via settings, use the steps provided below
### This is only required if currently running an April or eariler SPL. If already running latest stock, just install as usual
* First, grab the latest bootloader and modem images, found [in the zip of the May 2026 factory images here](https://developers.google.com/android/images)
* Once obtained follow the below steps:
1. Reboot bootloader
2. Flash the bootloader and modem images like follows:
```
fastboot flash bootloader bootloader-blazer-deepspace-17.1-15016913.img --slot all
fastboot flash radio radio-blazer-g5400i-251201-260127-b-14784805.img --slot all
fastboot reboot bootloader
```
*Note: rebooting bootloader / rebooting recovery may take a few extra seconds, do not be alarmed*
3. If successful, fastboot bootloader mode should reboot with the newest bootloader. Use arrow keys to reboot to recovery

4. ADB sideload v12.10 (or later) zip file (refer below if needed). Once sideloaded, reboot to recovery and sideload the same ROM file *again*

5. On the second sideload completion, you may then reboot recovery, sideload gapps and addons, and reboot system!
# Be aware once followed you may not return to 12.9 or below, or any other ROM that has not incremented bootloader, or you will brick!!!

### Pre-installation
* Download the latest ROM file (referred to as **crdroid.zip**).
* Download support files from the site:
  - **boot.img**
  - **dtbo.img**
  - **vendor_kernel_boot.img**
  - **vendor_boot.img** (this is the recovery image file)
* Download the latest GApps (referred to as **gapps.zip**).

*(Files may have YYYYMMDD date in file name or folder, download latest files in that case)*

---

### Step 1: Unlock Bootloader
**This step can be skipped if bootloader is already unlocked.**

1. Enable **OEM unlock** in the Developer options under device Settings, if present.

2. Connect the device to your PC via USB.

3. On the computer, open a command prompt (on Windows) or terminal (on Linux or macOS) window, and type:

```
adb -d reboot bootloader
```
*(You can also power off the device, and boot it into bootloader mode by holding **Volume Down + Power**)*

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

1. Download and keep support files (mentioned in pre-installation) ready.

2. On the computer, open a command prompt (on Windows) or terminal (on Linux or macOS) window, and type:

```
adb -d reboot bootloader
```
*(You can also power off the device, and boot it into bootloader mode by holding **Volume Down + Power**)*

3. Flash the downloaded image files to your device by typing:

```
fastboot flash boot boot.img
fastboot flash dtbo dtbo.img
fastboot flash vendor_kernel_boot vendor_kernel_boot.img
fastboot flash vendor_boot vendor_boot.img
```
*(If support files have YYYYMMDD date prefix, rename respective img file accordingly)*

### Step 3: Flash ROM and Gapps
**This step can be also used for update installation**

1. Ensure you have downloaded latest crdroid.zip package from the link above

2. If you are not in recovery, reboot into recovery:
  - With the device powered off, hold **Volume Down + Power**. Then use the menu to select **Recovery** mode.

3. For clean / first-time installation - Tap **Factory Reset** > **Format data** and continue with the formatting process. This will remove encryption and delete all files stored in the internal storage, as well as format your cache partition (if you have one). This step can be skipped for update installation.

4. Return to the main menu.

5. Sideload the crdroid.zip package but do not reboot before you read/followed the rest of the instructions!
  - On the device, tap **Apply Update** > **Apply from ADB** to begin sideload.
  - On the host machine, sideload the package using:

```
adb -d sideload crdroid.zip
```

6. After installing ROM package, recovery will ask reboot in recovery again for installing additional packages, reboot in recovery and
  - On the device, tap **Apply Update** > **Apply from ADB** to begin sideload.
  - On the host machine, sideload the package using:

```
adb -d sideload gapps.zip
```

6.5 If installing an ak3 kernel like WildKernel, you can flash it now using the same adb command as above

---

### Update Installation
* If you're updating to a newer version, you can either:
  - **Via OTA**: Use the in-built **Updater**. (Settings > System > Update)
  - **Via Recovery**: Follow **Step 3** above **without factory reset**.

*(No need to flash GApps again if updating via OTA, only required for recovery flashing)*

