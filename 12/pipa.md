### Pre-installation:

* Download latest ROM package (rom.zip)
* Download **boot.img**, **dtbo.img**, **vendor_boot.img** (links mentioned in ROM post)
* Flash latest firmware (if not already included in ROM)
* Optional GApps  (referred to as **gapps.zip**).
* Optional custom recovery (TWRP/OrangeFox) 
* Make sure bootloader is unlocked

Put all downloaded files in a single folder (recommended: platform-tools folder).

---

### First time installation (clean flash):

* Step 1: Reboot device into bootloader

```
adb reboot bootloader
```

*(or hold Power + Volume Down while device is off)*

* Step 2: Flash required images

```
fastboot flash boot boot.img
fastboot flash dtbo dtbo.img
fastboot flash vendor_boot vendor_boot.img
```

* Step 3: Reboot into recovery

```
fastboot reboot recovery
```

* Step 4: In recovery, **Format Data** (optional if flashing over same ROM, required for first time clean install)

* Step 5: From recovery menu → select **Reboot to recovery** (Advanced → Reboot to recovery)

* Step 6: Select **Apply update** → **Apply from ADB**, then sideload firmware

```
adb sideload firmware.zip
```

*(replace firmware.zip with actual filename)*

* Step 7: (Optional) Reboot recovery again, select **Apply update** → **Apply from ADB**, then sideload ROM package

```
adb sideload rom.zip
```

*(replace rom.zip with actual filename)*

* Step 8: (If flashing Vanilla build) Reboot recovery after ROM install ends at ~47% on PC terminal, then sideload GApps:

```
adb sideload gapps.zip
```

* Step 9: Reboot system

---

### Update installation:
* If you're updating to a newer version, you can either:
  - **Via OTA**: Use the in-built **Updater**. (Settings > System > Update)
  - **Via Recovery**: Follow **Step 2** above **without factory reset**.

*(No need to flash GApps again unless newer version of gapps is available)*
