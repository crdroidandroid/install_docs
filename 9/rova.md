### Pre-installation:

* OrangeFox recovery
    - [Download for Redmi 4A (rolex)](https://forum.xda-developers.com/t/unofficial-recovery-rolex-riva-orangefox-recovery-project-12-06-22-r11-1_1-fde-fbe.4457411/)
    - [Download for Redmi 5A (riva)](https://forum.xda-developers.com/t/unofficial-recovery-rolex-riva-orangefox-recovery-project-12-06-22-r11-1_1-fde-fbe.4457413/)
* Gapps ([Download from here](https://nikgapps.com/downloads))
* Magisk 20.0 or newer for root (after first boot) - ([Download from here](https://forum.xda-developers.com/apps/magisk/official-magisk-v7-universal-systemless-t3473445))
* Firmware
    - [Download for Redmi 4A (rolex)](https://sourceforge.net/projects/xiaomi-firmware-updater/files/Stable/V10/rolex/fw_rolex_miui_HM4AGlobal_V10.2.3.0.NCCMIXM_69d07208fd_7.1.zip/download)
    - [Download for Redmi 5A (riva)](https://sourceforge.net/projects/xiaomi-firmware-updater/files/Stable/V10/riva/fw_riva_miui_HM5AGlobal_V10.1.1.0.NCKMIFI_8cb19207b7_7.1.zip/download)

### First time installation (clean flash):

1. Install *OrangeFox* recovery from the *"Pre-installation"* section or any other recovery with FBE encryption support
2. Download the latest crDroid ROM & the latest Gapps package *(Optional)*
3. Boot into recovery
4. Perform a wipe of:
   - Dalvik / ART Cache
   - System
   - Vendor
   - Cache
5. **Format data is MANDATORY using OrangeFox recovery (or any other recovery with FBE encryption support).**
   > 💡 NOTE
   >
   > If you are upgrading from crDroid 8, you only need to wipe data.
6. Flash crDroid ROM
   > 🚨 IMPORTANT
   >
   > **The ROM is encrypted by default. This is a crDroid requirement!**
   > **If you don't care about encryption, you can disable it within OrangeFox recovery: [demonstration](https://imgur.com/nexuU1q) (you should see "Disable FBE" button instead).**

   > 💡 NOTE
   >
   > **Encrypting via the ROM's settings is no longer supported in Android 13+, so you will not be able to enable encryption in any other way (except clean install or as shown in the demo above).**
7. Flash Android 7 (Nougat) based firmware from the *"Pre-installation"* section
8. Flash Gapps [NikGapps T ARM64-Core] *(Optional)*
9. Flash Magisk Root *(Optional)*
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
