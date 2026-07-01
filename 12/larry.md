### Pre-installation:

* Make sure you have the ROM zip, latest OxygenOS firmware and recovery images.
* Download [copy-partitions-20220613-signed.zip](https://mirrorbits.lineageos.org/tools/copy-partitions-20220613-signed.zip) if you are on CPH246x.15.0.0.1600 or newer firmware.
* GApps package (optional) (from download page, GApps button).
* For KernelSU Next [here](https://sourceforge.net/projects/larry-rom-archive/files/UsefulTools/KernelSU_Next_v3.2.0-21-g5a4a7187_33150-release.apk/download)

> **WARNING:** If you are on **CPH246x.15.0.0.1600 or newer firmware**, you **MUST** flash *copy-partitions-20220613-signed.zip* before installing the ROM. Skipping this step will result in an installation failure and may leave the device hard-bricked, requiring EDL recovery. Do not proceed without completing this step.

### First time installation (clean flash):

* Go to bootloader (*adb reboot bootloader*).
* Flash the required images:

  ```
  fastboot flash boot boot.img
  fastboot flash dtbo dtbo.img
  fastboot flash vendor_boot vendor_boot.img
  fastboot flash vbmeta vbmeta.img
  ```
* Reboot to recovery (*fastboot reboot recovery*).
* Format data.
* Go to **Apply Update → Apply from ADB**.
* If you are on CPH246x.15.0.0.1600 or newer firmware, sideload [copy-partitions-20220613-signed.zip](https://mirrorbits.lineageos.org/tools/copy-partitions-20220613-signed.zip):

  ```
  adb sideload copy-partitions-20220613-signed.zip
  ```
* Once completed, reboot back to recovery.
* Go to **Apply Update → Apply from ADB** again.
* Sideload the ROM zip:

  ```
  adb sideload rom.zip
  ```
* Get a coffee while it's installing.
* After installation, if you want GApps, reboot to recovery again and sideload *gapps.zip* like the ROM zip.
* After all, reboot the system.
* And you got it!

### Update installation:

#### Via recovery (recommended way):

* Reboot to recovery.
* Sideload *rom.zip*.
* Reinstall GApps (if you had them before).
* Wipe cache and reboot to system.

#### Via OTA:

* Go to **Settings → System → Updater** and download the latest build.
* Choose install and let it finish.
* If having GApps, reboot to recovery and reinstall the GApps package again.
* Reboot to system.
