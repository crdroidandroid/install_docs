### Pre-installation:

* OrangeFox recovery
    - [Download for Redmi 4A (rolex)](https://forum.xda-developers.com/t/unofficial-recovery-rolex-riva-orangefox-recovery-project-12-06-22-r11-1_1-fde-fbe.4457411/)
    - [Download for Redmi 5A (riva)](https://forum.xda-developers.com/t/unofficial-recovery-rolex-riva-orangefox-recovery-project-12-06-22-r11-1_1-fde-fbe.4457413/)
* Gapps ([Download from here](https://nikgapps.com/downloads))
* Magisk 20.0 or newer for root (after first boot) - ([Download from here](https://forum.xda-developers.com/apps/magisk/official-magisk-v7-universal-systemless-t3473445))
* KernelSU (KSU) (NOTE: KernelSU-NEXT replaced KernelSU since crDroid 10.12)
    - [Download for crDroid 10.11 or lower](https://github.com/tiann/KernelSU/releases/download/v1.0.1/KernelSU_v1.0.1_11928-release.apk)
    - [Download for crDroid 10.12 or newer](https://github.com/rifsxd/KernelSU-Next/releases/download/v1.0.3/KernelSU_Next_v1.0.3_12264-release.apk)
* Firmware
    - [Download for Redmi 4A (rolex)](https://sourceforge.net/projects/xiaomi-firmware-updater/files/Stable/V10/rolex/fw_rolex_miui_HM4AGlobal_V10.2.3.0.NCCMIXM_69d07208fd_7.1.zip/download)
    - [Download for Redmi 5A (riva)](https://sourceforge.net/projects/xiaomi-firmware-updater/files/Stable/V10/riva/fw_riva_miui_HM5AGlobal_V10.1.1.0.NCKMIFI_8cb19207b7_7.1.zip/download)

### First time installation (clean flash):

1. Install *OrangeFox* recovery from the *"Pre-installation"* section or any other recovery with FBEv2 encryption support
2. Download the latest crDroid ROM & the latest Gapps package *(Optional)*
3. Boot into recovery
4. Perform a wipe of:
   - Dalvik / ART Cache
   - System
   - Vendor
   - Cache
5. **Format data is MANDATORY using OrangeFox recovery (or any other recovery with FBEv2 encryption support).**
6. Flash crDroid ROM
   > 🚨 IMPORTANT
   >
   > **The ROM is encrypted by default. This is a crDroid requirement!**
   > **If you don't care about encryption, you can disable it within OrangeFox recovery: [demonstration](https://imgur.com/nexuU1q) (you should see "Disable FBE" button instead).**
7. Flash Android 7 (Nougat) based firmware from the *"Pre-installation"* section
8. Flash Gapps [NikGapps T ARM64-Core] *(Optional)*
9. Flash Magisk Root/KernelSU *(Optional)*
10. Reboot to the system

### Update installation:

#### OTA

Check `Settings` > `System` > `Updater`

#### Local Update

Check `Settings` > `System` > `Updater` > `Three dots` > `Local Update`

#### Recovery

1. Download the latest crDroid ROM
2. Reboot to recovery
3. Flash crDroid update
   > 💡 NOTE
   >
   > Read recovery logs and make sure Gapps and/or Magisk have restored themselves.
4. Wipe Dalvik / ART Cache
5. Reboot to the system
