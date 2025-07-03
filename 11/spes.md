### Pre-installation:

* Make sure you have the latest firmware available for your phone (from download page, firmware button).
* Gapps package (optional) (from download page, gapps button)
* Recovery (from download page, recovery button). If you want to use crDroid recovery then download both boot.img and vendor_boot.img, after that you can flash them in fastboot (Power + Volume Down) by doing **fastboot flash boot boot.img** and **fastboot flash vendor_boot vendor_boot.img**, then you can proceed with **fastboot reboot recovery**
* A pc with platform-tools working (adb/fastboot) 

### Unlock Bootloader
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

---

**First time installation (clean flash)**

### Step 1: Flash crDroid

Boot into **Recovery Mode** (Power + Volume Up)

---

### Step 2: Wipe Data

In recovery:

Factory reset → Format data/Factory Reset → "Format data"

---

### Step 3: Flash ROM

* Copy the ROM .zip to internal storage (or use sideload)
* In crDroid Recovery:
* Apply update
* In your computer either cmd or terminal do **adb sideload filename.zip** 

Example: 

```
adb sideload crDroidAndroid-15.0-20250629-spes-v11.6.zip
```
* Click enter and wait for flash to finish.

---

### Step 4: Flash GApps (Optional)

* Only if you want to use Google Apps
* Flash GApps .zip immediately **after ROM**, without reboot. But when asked to reboot to recovery then you can, after that you can click Apply update and proceed with: 

```
adb sideload MindTheGapps-15.0.0-arm64-20250214_082511.zip
```
---

### Step 5: Reboot

* Go back to main menu
* Select Reboot → System

*First boot will take a few minutes.*

---

### Update Installation
* If you're updating to a newer version, you can either:
    - **Via OTA**: Use the built-in **Updater**. (Settings > System > Update)
    - **Via Recovery**: Follow **Step 3** above **without factory reset**.

*If you are encountering Google Play Services/Play Store crashing after update then proceed with flashing GApps again via recovery. Follow **Step 4** for flashing GApps*.
