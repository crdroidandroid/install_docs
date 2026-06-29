### Pre-installation:
* Make sure you have the ROM zip, latest RealmeUI firmware and recovery images.
* Download copy-partitions-signed.zip if you are on RMX3151export_13.f18 or newer firmware.
* Gapps package (optional) (from download page, gapps button).

### First time installation (clean flash):
* Go to bootloader (adb reboot bootloader).
* Flash boot.img and vendor_boot.img (exp: fastboot flash boot boot.img).
* After that reboot to recovery (fastboot reboot recovery).
* Format data.
* Go to Apply Update -> Apply from ADB.
* If you are on RMX3151export_13.f18 or newer firmware, sideload copy-partitions-signed.zip (adb sideload copy-partitions-signed.zip).
* Once completed, reboot back to recovery.
* Go to Apply Update -> Apply from ADB again.
* Sideload the ROM zip (adb sideload rom.zip).
* Get a coffee while it's installing.
* After installation, if you want GApps, reboot to recovery again and sideload gapps.zip like the ROM zip.
* After all, reboot the system.
* And you got it!

### Update installation:
#### Via recovery (recommended way):
* Reboot to recovery.
* Sideload rom.zip.
* Reinstall GApps (if you had them before).
* Wipe cache and reboot to system.

#### Via OTA:
* Go to Settings -> System -> Updater and download the latest build.
* Choose install and let it finish.
* If having GApps, reboot to recovery and reinstall the GApps package again.
* Reboot to system.
