### Pre-Installation:

- We're now using retrofitted dynamic partitions to allow larger ROMs & Google Apps packages. Don't panic. This will not permanently alter or damage your device, and following any ROM's installation guide will overwite the changes, so there are no extra steps to "convert back to normal partitions".

  This does mean that you cannot use TWRP or other custom recovery to install crDroid on the OnePlus 6-series, as they do not have the necessary kernel and dynamic partition layout changes compiled in to support the way we're doing things.

- Phone setup:

  Make sure you have tested all functions in stock OxygenOS (VoLTE, VoWiFi, Camera, Bluetooth, GPS, etc.) before unlocking bootloader to install custom ROMs so that your device will be provisioned correctly for IMS services and such.

  Bootloader must be [unlocked](https://xdaforums.com/t/oneplus-6-unlock-bootloader-flash-twrp-root-nandroid-efs-backup.3792643/). Re-locking after installation is not supported.

  Must have [OxygenOS 11.1.2.2 firmware](https://otafsg1.h2os.com/patch/amazone2/GLO/OnePlus6Oxygen/OnePlus6Oxygen_22.J.62_GLO_0620_2111252336/OnePlus6Oxygen_22.J.62_OTA_0620_all_2111252336_14afec75dd6fa.zip) in your current slot.
  This does NOT mean you need to go back to stock first.
  It DOES mean that you have updated firmware partitions since the last time using MSMTool or a "back to stock" fastboot ROM zip.
  If you're not sure, follow the firmware updating guide for enchilada from the LineageOS wiki [here](https://wiki.lineageos.org/devices/enchilada/fw_update/), or [use MSMTool](https://xdaforums.com/t/op6-latest-10-3-8-collection-of-unbrick-tools.3914109/) to go back to stock OxygenOS with locked bootloader and start updating via OTA until you're up to date.

- Computer setup:

  Must have current AOSP "platform-tools" installed and/or on your $PATH.

  Use current release from [developer.android.com](https://developer.android.com/studio/releases/platform-tools.html), not "all in one" bundles or out-of-date packages from your Linux distro.

  Must have working adb/fastboot USB drivers.

  For Windows: You need to install [OnePlus USB drivers](https://drive.google.com/file/d/1L7EZGx5mgeQYXO19Vsp9FWu9GXhF45Qs/view) for fastboot in OEM Bootloader, and [Google USB drivers](https://developer.android.com/studio/run/win-usb) for "userspace fastboot" environment within crDroid Recovery.

  NOTE: Use of PowerShell [v7.x or newer](https://github.com/PowerShell/PowerShell/releases), and [Windows Terminal](https://apps.microsoft.com/detail/9N0DX20HK701?hl=en-us&gl=US&ocid=pdpshare) is highly recommended.

  NOTE: PowerShell might require you to replace every instance of `./fastboot` with `./fastboot.exe`, and `./adb` with `./adb.exe` in the commands below.

  For Linux or MacOS: Drivers included in any release within the last few years typically work already.

  For more info/troubleshooting, see [the adb and fastboot guide](https://wiki.lineageos.org/adb_fastboot_guide) on the LineageOS wiki.

- Required files:

  On download page, click on "Download older versions" button to see complete file download list. You will need:

  "crDroidAndroid-xxx_boot.img"

  "crDroidAndroid-xxx_dtbo.img"

  "crDroidAndroid-xxx_super_empty.img"

  "crDroidAndroid-xxx_vbmeta.img"

  "crDroidAndroid-xxx.zip"

  These file names are examples, with "xxx" replacing variable strings like dates & versions.

  Each release includes updated boot, dtbo, super_empty, and vbmeta img files. Make sure you download a matched set that all have the same version and date in the file name. Do not mix & match.

- Optional files:

  Google Apps or microG installer zip (see download page for recommended link, or support forum for more options).

  PROTIP: Save a copy of the Google Apps or microG zip file with your computer backups. It is likely you will need to flash from recovery at a later date; you will need this file!

  NOTE: "Disable_Dm-Verity_ForceEncrypt" or other attempts to disable userdata encryption are both unsupported and ***highly*** discouraged.


### First Time Installation (Clean Flash):
_Coming from any other ROM or major Android version_

***WARNING: The first-time installation process includes formatting userdata, which will erase all contents of the phone's internal storage. Back up all data (photos, downloads, messages, etc.) that you wish to keep before proceeding.***

Notice that each command is prefixed with a ***"./"***. This is important. Please keep that prefix when you run each command.
_(unless you know how to add things to your $PATH and can verify which executable is running, of course)_

- Step 1: On the computer, unzip the "platform-tools-latest-xxx.zip" file you downloaded earlier to any directory from which you can run programs.

- Step 2: On the computer, move the downloaded files into the extracted "platform-tools" directory (so that they are in the same place as the adb and fastboot executable files), and rename the ".img" files as shown below:

  "crDroidAndroid-xxx_boot.img" renamed to "boot.img"

  "crDroidAndroid-xxx_dtbo.img" renamed to "dtbo.img"

  "crDroidAndroid-xxx_super_empty.img" renamed to "super_empty.img"

  "crDroidAndroid-xxx_vbmeta.img" renamed to "vbmeta.img"

  "crDroidAndroid-xxx.zip" (do not rename)

  (optional) the Google Apps or microG installation zip you decided to use (do not rename)

- Step 3: On the computer, open the terminal app and navigate to the extracted "platform-tools" directory.

  If you are using Windows, you must install PowerShell 7. Do NOT use Command Prompt; it will not work correctly.

  If you are using MacOS or Linux, use your preferred terminal and shell.

- Step 4: Boot the phone to OEM bootloader.

  Unplug USB cable from the phone, power it off completely, then hold all three hardware buttons (Vol Up + Vol Down + Power) until you see a screen with large green "Start" text at the top of the display. Release all buttons.

  NOTE: Verify you have working OnePlus USB drivers now by plugging the USB cable back in, and running the following terminal command:

  ```
  ./fastboot devices
  ```

  You should see the phone's serial number in the list of devices attached. If not, troubleshooting options include reinstalling drivers, trying a different cable, or a different USB port, or a USB hub, or modifying udev rules, and so on until it works correctly.

- Step 5:

  Run the following terminal command (flashes the necessary partitions to boot crDroid recovery successfully with needed retrofit dynamic partition support for ROM install, and prepares GPT partitions that will become the backing store for super partition):

  ```
  ./fastboot flash boot_a boot.img && ./fastboot flash boot_b boot.img && ./fastboot flash dtbo_a dtbo.img && ./fastboot flash dtbo_b dtbo.img && ./fastboot flash vbmeta_a vbmeta.img && ./fastboot flash vbmeta_b vbmeta.img && ./fastboot erase system_a && ./fastboot erase system_b && ./fastboot erase odm_a && ./fastboot erase odm_b && ./fastboot erase vendor_a && ./fastboot erase vendor_b
  ```

  NOTE: You will see a message after running the "./fastboot erase" commands asking if you meant to format instead. You can safely disregard this message.

- Step 6: Unplug the USB cable & reboot the phone into recovery.

  Use the volume buttons to page through the boot options until you see "Recovery mode". Press the power button to select that option.

  NOTE: The phone might vibrate and reboot to the "Bootloader Unlocked" splash screen twice before entering recovery. This is normal, and is a result of the two-stage init process our kernel uses for enabling dynamic partition support.

- Step 7: On the phone, you should see the crDroid Recovery screen (white text with orange accent colors on black background). Tap to choose "Advanced" then "Enter fastboot" to enter "userspace fastboot" mode, and plug the USB cable back into phone.

  NOTE: Verify the computer has working USB drivers for "userspace fastboot" mode now by running the following terminal command:

  ```
  ./fastboot devices
  ```

  You should see the phone's serial number in the list of devices attached. If not, follow typical USB device driver troubleshooting as needed, same as before.

- Step 8: Run the following terminal commands (initializes the retrofit super partitions with metadata for this ROM's configuration, in both slots):

  ```
  ./fastboot --slot a wipe-super super_empty.img
  ```

  then

  ```
  ./fastboot --slot b wipe-super super_empty.img
  ```

  WARNING: If fastboot on the computer returns an error message about not recognizing "wipe-super" or prints a long help message instead, then that means you are either running a very old version of the fastboot executable or the phone is still in OEM bootloader instead of recovery-based fastbootd. Please go back and download the latest version of platform-tools as mentioned in the "Required files" section, and/or fix the computer's driver situation so that you can send fastboot commands while the phone is in "Enter fastboot" mode from within crDroid Recovery. This is NOT optional.

- Step 9: Choose "Enter recovery" on the phone to return to recovery, then choose "Apply update" then "Apply from ADB" so that the phone is waiting to receive a sideloaded installation package from the computer.

- Step 10: On the computer, run the following terminal command to sideload crDroid Android, substituting the actual zip file name:

  ```
  ./adb sideload crDroidAndroid-xxx.zip
  ```

  Normally the process will pause at 47% on the computer, and on the phone you will be prompted to reboot to recovery again in order to continue flashing addons (such as Google Apps or microG, since those are not built into crDroid).

  Choose "Yes" on the phone to reboot into recovery. When the phone reboots, the "adb sideload" process on computer will complete at 47%, possibly with an error message about "no error", and give you a prompt again. This is "normal".

  NOTE: If you encounter any other installation errors when sideloading besides ROM zip sideloading stopping at 47%, please run the following command in terminal to save recovery logs before asking for help:

  ```
  ./adb pull -a /tmp/recovery.log
  ```

- Step 11: Once the phone has rebooted back into recovery, choose "Apply update" then "Apply from ADB" again.

- Step 12: Run the following terminal command to sideload crDroid Android a second time (so it gets written to the other slot), again substituting the actual zip file name:

  ```
  ./adb sideload crDroidAndroid-xxx.zip
  ```

  Choose "Yes" again on the phone when prompted to reboot back into recovery.

- Step 13 (Optional): If you want to use Google Apps or microG, now is the time to install the zip from "Optional Files" above.

  On the phone, choose "Apply update" then "Apply from ADB" again, and on the computer, run the following terminal command, substituting the actual zip file name:

  ```
  ./adb sideload gapps-or-microg-install-package.zip
  ```

- Step 14: Since this is a clean install, navigate back to the top level menu of recovery on the phone, choose the "Factory reset" option, and confirm.

  NOTE: This is not optional if you want support.

- Step 15: Disconnect the USB cable, navigate back to the top level menu of recovery on the phone, and choose "Reboot system now" to begin first boot.

  NOTE: The phone might vibrate and reboot to the "Bootloader Unlocked" splash screen twice before the crDroid boot animation begins. This is normal, and is a result of the two-stage init process our kernel uses for enabling dynamic partition support.

- Step 16: Post-installation recommendations:

  OnePlus 6-series hardware seems to respond best if you reboot as quickly as possible after completing the first boot Setup Wizard when doing a clean install. Finish tweaking settings after.

  If using Google Apps, you can skip restoring data during first boot Setup Wizard, because it will prompt again to "Continue setting up this device" after rebooting once (as mentioned above).

  Disable NFC unless you're actually using it. Google likes to enable this and hide the setting now.

### Update Installation:
_Updating to a newer release of the same major Android version_


***Option 1: From OTA Updater***

_(Processes addon.d OTA survival scripts, so addons such as Google Apps / microG / Magisk that install survival scripts to "/system/addon.d/" should be preserved automatically)_

- Step 1: Open "Settings > System > System Updates" on the phone. Before loading an update to install, choose "Preferences" from the menu and turn on the "Prioritize update process" and "Delete updates when installed" toggles.

  PROTIP: Use the "Caffeine" Quick Settings tile to keep the screen on for at least 10 minutes, or just temporarily set the Display timeout to 10 minutes to speed up the process. Installation slows down drastically if the screen turns off.

- Step 2: Now either check for updates, or choose "Local update" from the menu & select the desired ROM zip file from the phone's internal storage. Once the installer has verified the update, choose "Install" to begin installation.

- Step 3: Reboot once installation has completed. If the phone screen has turned off or you navigated away from the "System updates" activity to use another app, then the only indication that updating has completed will be that the notification with progress bar has disappeared. Don't panic; just reboot the phone and you should see that the update has been applied.

- Step 4 (Optional): If using Terminator_J's "crDroid++" kernel, reboot to recovery and follow the "adb sideload" procedure to flash the kernel zip which matches the ROM zip version you just installed (see Option 2 - Step 5 below for example).

  NOTE: This will never be automated with an addon.d OTA survival script. Since KernelSU support has to be compiled into the kernel image itself, including a script that restores an older version of the kernel image would defeat the purpose of updating.

- Step 5: Disconnect the USB cable, navigate back to the top level menu of recovery on the phone, and choose "Reboot system now" to continue using crDroid.


***Option 2: From Recovery***

_(Does NOT process OTA survival scripts, so you MUST manually re-flash installer zips for any addons you need, such as Google Apps)_

- Step 1: Make sure you have the **same Google Apps or microG installation zips** available to sideload (or updated versions of the same Android version/architecture for your preferred package) as when you performed the initial clean installation. If you try to change to a different GApps bundle now, things will likely break.

- Step 2: Reboot the phone to recovery and connect USB cable to the computer once crDroid recovery has started (white text & orange accent colors on black background).

  Tap to choose "Apply update" then "Apply from ADB" so that the phone is waiting to receive a sideloaded installation package from the computer.

- Step 3: On the computer, run the following terminal command to sideload crDroid Android, substituting the actual zip file name:

  ```
  ./adb sideload crDroidAndroid-xxx.zip
  ```

  Normally the process will pause at 47% on the computer, and on the phone you will be prompted to reboot to recovery again in order to continue flashing addons (such as Google Apps or microG, since those are not built into crDroid).

- Step 4: Choose "Yes" on the phone to reboot into recovery. When the phone reboots, the "adb sideload" process on computer will complete at 47%, possibly with an error message about "no error", and give you a prompt again. This is "normal".

  NOTE: If you encounter any other installation errors when sideloading besides ROM zip sideloading stopping at 47%, please run the following command in terminal to save recovery logs before asking for help:

  ```
  ./adb pull -a /tmp/recovery.log
  ```

  WARNING: If you are using Google Apps or microG, DO NOT SKIP REBOOTING TO RECOVERY TO INSTALL ADDONS. DO NOT INSTALL ADDONS BEFORE REBOOTING TO RECOVERY. This is REQUIRED due to how slot-switching works.

- Step 5: If you have been using any addons (Google Apps, microG, custom kernel zips, etc.) now is the time to install them into the freshly-flashed slot so that they will continue working. On the phone, choose "Apply update" then "Apply from ADB" again, and on the computer, run the following terminal command, substituting the actual zip file name:

  ```
  ./adb sideload gapps-or-microg-install-package.zip
  ```

  Repeat the adb sideload process for all addon zip files you need to reinstall.

  WARNING: Recovery installation ***does NOT process addon.d OTA survival scripts*** (unlike the regular OTA updater in "Settings > System > System updates", which does), so ***you CANNOT skip installing the Google Apps zip now*** if you previously had them installed; or your current installation will be broken and you will need to either factory reset or wipe runtime permissions.

- Step 6: Disconnect the USB cable, navigate back to the top level menu of recovery on the phone, and choose "Reboot system now" to continue using crDroid.


_(Instructions adapted with permission from the dynamic partitions conversion guide originally by jabashque and AnierinBliss, with extensive adaptation & updating over the years by Terminator\_J)._
