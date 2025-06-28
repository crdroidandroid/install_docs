## 🧰 Flashing Instructions

### Pre-installation:

* Make sure you have the latest firmware available for your phone (from download page, firmware button).
* Gapps package (optional) (from download page, gapps button)
* Recovery (from download page, recovery button)
* A pc with platform-tools working (adb/fastboot)

---

* Flash recovery with the custom recovery you already have and reboot to it

### Step 1: Flash crDroid

Boot into **Recovery Mode** (`Power + Volume Up`)

---

### Step 2: Wipe Data

In recovery:

```
Factory reset → Format data/Factory Reset → Tap "yes"
```

---

### Step 3: Flash ROM

* Copy the ROM `.zip` to internal storage (or use sideload)
* In crDroid Recovery:

  * `Apply update`
  * In your computer either cmd or terminal do **adb sideload filename.zip** 

Example: 

```
adb sideload crDroidAndroid-15.0-20250628-spes-v11.6.zip
```
  * Click enter and wait for flash to finish.

---

### Step 4: Flash GApps (Optional)

* Only if you want to use Google Apps
* Flash GApps `.zip` immediately **after ROM**, without reboot. But when asked to reboot to recovery then you can, after that you can click `Apply update` and proceed with `adb sideload gapps.zip` depending on what the filename of your gapps zip file is.

---

### Step 5: Reboot

* Go back to main menu
* Select `Reboot → System`

*First boot will take a few minutes.*
