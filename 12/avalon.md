### Pre-installation
* Download the latest crDroid zip.
* Download the additional partitions needed for flashing:
  - **boot.img**
  - **dtbo.img**
  - **vbmeta.img**
  - **vendor_boot.img**
  - **recovery.img**
* Download GApps (optional)

**Warning:** Your device needs a specific firmware version before proceeding.

If your device is currently using a newer or older version than the required version, please up- or downgrade to the required version before proceeding with this installation.

The required version is **Android 15**, which may be lower than the crDroid version you are about to install - this is not an error!
If there are multiple updates of that version (e.g. security updates), make sure to use the latest!

If you need to upgrade or downgrade your device, please search online for guides.
We are unable to provide specific instructions here and on our support platforms.

### Step 1: Unlocking the bootloader
**This step can be skipped if the bootloader is already unlocked.**

1. Enable **OEM unlocking** and **USB Debugging** in developer settings.

2. With the device connected to the PC via USB, run:

```
adb -d reboot bootloader
```

3. After entering the bootloader mode, confirm the device is recognized by the computer, by doing:
 
```
fastboot devices
```
4. Now enter the following command to unlock the bootloader:

```
fastboot flashing unlock
```
 - The device will completely reset, so make sure to re-enable **USB Debugging** after rebooting.
 
### Step 2: Flashing the additional partitions and the crDroid recovery
**You can skip this step if you have a custom recovery, like TWRP or OFRP.**

1. Enter the following command on the computer to enter fastboot mode:

```
adb -d reboot bootloader
```

2. After you entered fastboot mode, start flashing the additional partitions, by doing:

```
fastboot flash boot boot.img
fastboot flash dtbo dtbo.img
fastboot flash vbmeta vbmeta.img
fastboot flash vendor_boot vendor_boot.img
fastboot flash recovery recovery.img
```

3. Once the additional partitions and recovery are flashed, use the **Volume keys** to select **Recovery**, and **Power button** to select.


## Step 3: Flashing the ROM
**This step can be also used for update installation**

1. Make sure you are in recovery. If you are not, with the device powered off, enter the button combination **Volume Down + Power**.

2. If clean flashing, select **Factory Reset** > **Format data**.

3. Return to the main menu of the recovery.

4. Sideload the crdroid.zip package but do not reboot before you read/followed the rest of the instructions!
  - On the device, tap **Apply Update** > **Apply from ADB** to begin sideload.
  - On the computer, sideload the package using:

```
adb -d sideload crdroid.zip
```

5. After the installation is done, you will be asked if you want to reboot recovery to install additional packages. (e.g GApps, root). If that is needed, press **Yes**, and flash additional packages in the same manner as the ROM,

### Update Installation
* If you're updating to a newer version, you can either:
  - **Via OTA**: Use the in-built **Updater**. (Settings > System > Update)
  - **Via Recovery**: Follow **Step 3** above **without factory reset**.

*(No need to flash GApps again if updating via OTA)*