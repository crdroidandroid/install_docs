## Installation Guide

### Important Information
- Do **not** flash custom recoveries (TWRP, OrangeFox, etc.)
- The boot and recovery are merged into one boot.img

### Requirements
- Unlocked bootloader  
- Latest firmware (your region)  
- ADB & Fastboot installed  

---

### 1. Flash Firmware
- Update to the latest stock firmware (Mi Flash Tool or fastboot).

---

### 2. Flash Boot Image

```bash
fastboot flash boot boot.img
```

### 3. Boot to Recovery
- Volume Up + Power

**OR**, use the following command:

```bash
fastboot reboot recovery
```
---

### 4. Flash ROM

```bash
adb sideload rom.zip
```

---

### 5. Format Data (Required)
- Do **not** reboot after flashing
- Select **No** if prompted
- Go and Format Data / Factory Reset

---

### 6. (Optional) Flash Add-ons

- GApps, kernels, etc:

```bash
adb sideload file.zip
```

---

### 7. Reboot

- Reboot to system.

--- 

### Via OTA:

- Go to **Settings -> System -> Updater** and download latest build
- Tap **Install** and let it finish
- If you have flashed GApps before, reboot to recovery and sideload the GApps package again  
- Reboot to system


### Notes
- First boot takes some time
- Clean flash recommended
