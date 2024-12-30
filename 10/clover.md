### Pre-installation
* Download the latest ROM file (referred to as **crdroid.zip**).
* Download the TWRP recovery (referred to as **recovery.img**).
* Download the latest NikGApps (referred to as **gapps.zip**).
* Ensure you are on latest available firmware for your device.

*(Files may have YYYYMMDD date in file name, download latest files in that case)*

---

### Step 1: Unlock Bootloader
**This step can be skipped if bootloader is already unlocked.**

1. Create a Mi account on **[Xiaomi’s website](https://global.account.xiaomi.com/pass/register)**. Beware that one account is only allowed to unlock one unique device every 30 days.  
2. Add a phone number to your Mi account.  
3. Insert a SIM into your phone.  
4. Enable developer options in **Settings** > **About Phone** by repeatedly tapping MIUI Version.  
5. Link the device to your Mi account in **Settings** > **Additional settings** > **Developer options** > **Mi Unlock status**.  
6. Download the **[Mi Unlock app](https://en.miui.com/unlock/download_en.html)** (Windows is required to run the app).  
7. Run the Mi Unlock app and follow the instructions provided by the app. It may tell you that you have to **wait up to 30 days**. If it does so, please wait the quoted amount of time before continuing to the next step!  
8. After device and Mi account are successfully verified, the bootloader should be unlocked.  
9. Since the device resets completely, you will need to re-enable USB debugging to continue.  

### Step 2: Flash Recovery 
**This step should be run at least once before coming from stock or any other custom ROM.**

1. Download and keep support files (mentioned in pre-installation) ready.  
2. On the computer, open a command prompt (on Windows) or terminal (on Linux or macOS) window, and type:

```
adb -d reboot bootloader
```

*(You can also power off the device, and boot it into bootloader mode by holding **Volume Down + Power**. Keep holding both buttons until the word “FASTBOOT” appears on the screen, then release.)*

3. Once the device is in fastboot mode, verify your PC finds it by typing:

```
fastboot devices
```

4. Flash the downloaded image files to your device by typing:

```
fastboot flash recovery recovery.img
```

*(If support files have YYYYMMDD date prefix, rename respective img file accordingly)*

4. Now reboot into recovery to verify the installation. Do **not** reboot into the existing OS, since it will overwrite the recovery you just installed!
  - With the device powered off, hold **Volume Up + Power**. Keep holding both buttons until the Xiaomi/POCO/Redmi splash appears appears on the screen, then release.

*Note: If your recovery does not show the TWRP logo, you accidentally booted into the wrong recovery. Please start at the top of this section!*

### Step 3: Flash ROM and NikGApps
**This step can be also used for update installation**

1. Ensure you have downloaded latest crdroid.zip package from the link above
2. If you are not in recovery, reboot into recovery:
  - With the device powered off, hold **Volume Up + Power**. Keep holding both buttons until the Xiaomi/POCO/Redmi splash appears on the screen, then release.
3. For clean / first-time installation - Tap **Wipe** > **Format data** and continue with the formatting process. This will remove encryption and delete all files stored in the internal storage, as well as format your cache partition (if you have one). This step can be skipped for update installation.  
4. Return to the main menu.  
5. Sideload the crdroid.zip package but do not reboot before you read/followed the rest of the instructions!  
  - On the device, tap **Advanced** > **ADB Sideload** to begin sideload.
  - On the host machine, sideload the package using:

```
adb -d sideload crdroid.zip
```

6. After installing ROM package, you can optionally flash gapps package. This step can be skipped for update installation.
  - On the device, tap **Advanced** > **ADB Sideload** to begin sideload.
  - On the host machine, sideload the package using:

```
adb -d sideload gapps.zip
```

---

### Update Installation
* If you're updating to a newer version, you can either:
  - **Via OTA**: Use the in-built **Updater**. (Settings > System > Update)
  - **Via Recovery**: Follow **Step 3** above **without factory reset**.

*(No need to flash NikGApps again unless newer version is available)*

