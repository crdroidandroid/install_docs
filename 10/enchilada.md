_Starting in crDroid 10.x (Android 14.0) we're switching to retrofitting dynamic partitions, to avoid the constant threat of running out of space in the GPT system partition with any sizeable Google Apps package._

_Please do not panic. Resist the temptation to read, or talk to loved ones._

_Have a cookie._

### Prerequisites

- Ensure you're running OxygenOS 11.1.2.2 firmware on your current slot. Instructions for how to do this are beyond the scope of this guide, but you can always use MSMTool to go back to stock OxygenOS with locked bootloader, and start updating via OTA until you're up to date, or follow the firmware updating guides for enchilada or fajita on the LineageOS wiki.

  If you do not have that firmware installed, grab it for your device from **[here](https://oxygenos.oneplus.net/OnePlus6Oxygen_22.J.62_OTA_0620_all_2111252336_287bcb1636d743d3.zip)**

- An unlocked bootloader (see Funk Wizard's guides in XDA Forums for instructions if you need help to do this), and the understanding that crDroid does not support re-locking the bootloader after installation on this device.

- A computer with current AOSP "platform-tools" installed or otherwise on your $PATH (the real ones from developer.android.com, not some script-kiddie's all-in-one bundle that's hopelessly out of date), OnePlus USB drivers installed (works for adb and OEM bootloader _fastboot_ commands), and Google's universal ADB drivers installed (needed for fastbootd mode within recovery). Linux and MacOS users: when it comes to drivers, may the odds be ever in your favor!

  If you do not have current platform-tools installed, get it from the official site **[here](https://developer.android.com/studio/releases/platform-tools)**

  If you do not have the OnePlus USB drivers for 6-series, get the installer **[here](https://drive.google.com/file/d/1L7EZGx5mgeQYXO19Vsp9FWu9GXhF45Qs/view)**

  If you do not have the generic Google USB drivers, download them **[here](https://developer.android.com/studio/run/win-usb)**

### Required Files

- Download the LineageOS copy-partitions script from **[here](https://mirrorbits.lineageos.org/tools/copy-partitions-20220613-signed.zip)**

- Download the needed files for you device from here **[here](https://sourceforge.net/projects/crdroid/files/enchilada/10.x/)**

- Required device files for first-time retrofit dynamic partitions conversion (or in the case of *dtbo.img*, to ensure you can boot if you've been playing with 4.19 kernel-based builds):
  - crDroidAndroid-14.0-xxx_boot.img
  - crDroidAndroid-14.0-xxx_dtbo.img
  - crDroidAndroid-14.0-xxx_super_empty.img
  - crDroidAndroid-14.0-xxx_vbmeta.img
  - ...and then the latest OTA zip for you device (crDroidAndroid-14.0-xxx.zip)

  *_Do \*\*\*NOT\*\*\* substitute \*any\* of these files with files that you've downloaded elsewhere if you want support for your installation._*

### Optional files

- Recommended Google Apps:

  Now that we have enough room thanks to dynamic partitions, we have options!

  MindTheGapps _should_ always be a good option, regardless of how much Pixel integration the crDroid dev team is including or not at the time:

  **[MindTheGapps 14.0.0-arm64](https://github.com/MindTheGapps/14.0.0-arm64/releases)**

  If you want a bit more Google integration, you can use Gabriel's "crdroid-official" NikGapps elite config. Download here:

  **[NikGapps recommended bundle](https://nikgapps.com/crdroid-official)**

- Magisk/crDroid++ Kernel for KernelSU support:

  - Let's save that kind of thing for after you've booted the first time & finished the Setup Wizard. Best to get a clean SafetyNet/Play Integrity attestation first, then reboot to recovery to flash root tools after.

- Disable_Dm-Verity_ForceEncrypt:

  - Go find a fire. Throw yourself in it. _Repeat until you learn better._

### Clean Installation/Retrofit Dynamic Partition Migration steps

Notice that each command is prefixed with a **./** This is important. Please keep that prefix when you run each command.
_... unless you know how to add things to your $PATH and can verify which executable you're running, of course_

1. Unzip the **platform-tools-latest-*.zip** file you got earlier to any folder that you want.

2. Move the following files into the extracted platform-tools directory (so that the ROM zip is in the same folder as adb & fastboot binaries, not one level above it or anything else):

  - Required device files for first-time installation:
    - copy-partitions-20220613-signed.zip
    - crDroidAndroid-14.0-xxx_boot.img
    - crDroidAndroid-14.0-xxx_dtbo.img
    - crDroidAndroid-14.0-xxx_super_empty.img
    - crDroidAndroid-14.0-xxx_vbmeta.img
    - the latest OTA zip for you device (crDroidAndroid-14.0-xxx.zip)

  - Optional addons:
    - the Android 14.0 arm64 Google Apps or microG installer zip you decided on (if any)

3. Open your terminal and navigate to the extracted platform-tools folder. Use **cd** to navigate to the folder.

  - If you are on Windows, use PowerShell (or Windows Terminal with an updated PowerShell 7 or later). Do ***NOT*** use Command Prompt.
  - If you are on macOS or Linux, then use your preferred terminal and shell.

4. Boot/Reboot your phone to the OEM bootloader.

  - Do this by unplugging your phone, powering it off, then holding Vol Up + Vol Down + Power until you see a screen with giant green text saying "Start" at the top of the screen.
  - Verify you have correctly installed OnePlus USB drivers by plugging the USB cable back in, and running **fastboot devices** from the terminal window. You should see your device's serial number in the list of devices attached. If not, try reinstalling drivers, try a different cable, or a different USB port until it works.

5. Run the following to flash the retrofit dynamic partitions boot/recovery image, dtbo image, and the empty vbmeta to the current slot (replacing _crDroidAndroid-14.0-xxx_thing.img_ with the actual filename that you downloaded for each file):

    ```
    ./fastboot flash boot crDroidAndroid-14.0-xxx_boot.img
    ./fastboot flash dtbo crDroidAndroid-14.0-xxx_dtbo.img
    ./fastboot flash vbmeta crDroidAndroid-14.0-xxx_vbmeta.img
    ```

6. Erase the old Android partitions in the current slot with the following:

   ```
   ./fastboot erase system
   ./fastboot erase odm
   ./fastboot erase vendor
   ```

  - This ensures that we erase any super partition metadata from other ROMs that use retrofit dynamic partitions, no matter if they store the metadata in system, odm, or vendor. If we don't do this, then we may end up encountering errors later on during the wipe-super or sideloading steps.

  - This needs to be done only for the current slot and not the other slot. The other slot is handled later in the process.

7. Unplug the USB cable & reboot your phone into recovery.

  - Do this by using the volume buttons to scroll through the options until you see **Recovery mode**. Press the power button to select that option.

8. In recovery, choose **Advanced -> Enter fastboot** to enter fastbootd ("userspace fastboot"), and plug the USB cable back in.

  - This is a good time to run **fastboot devices** to make sure that the userspace fastbootd drivers are working. If not, unplug & re-plug the USB cable again or check for driver updates via Device Manager or Windows Update.

9. Initialize the retrofit super partitions for the current slot:

    ```
    ./fastboot wipe-super crDroidAndroid-14.x-xxx_super_empty.img
    ```

  - When we sideload the crDroid ROM later, update_engine will handle initializing the other slot using the current slot's metadata.

WARNING: If fastboot returns some error message about not recognizing **wipe-super** or prints a long help message instead, then that means you are running a very old version of the fastboot executable. Please go back and download the latest version of platform-tools, as mentioned in the _Required Files_ section.

10. Choose **Enter recovery** to return to recovery.

11. While in recovery, navigate to **Apply update -> Apply from ADB**.

12. Run the following to sideload **copy_partitions.zip** to copy your firmware partitions to the other slot:

    ```
    ./adb sideload copy-partitions-20220613-signed.zip
    ```

  - You *may* receive an error from recovery, which will state the following:

    ```
    > Signature verification failed  
    > Install anyway?
    ```

  - Choose the "Yes" option to continue, since this zip doesn't have a signature in the first place.

13. Navigate to **Apply update -> Apply from ADB** again.

14. Run the following to sideload crDroid Android, substituting the actual zip file name:

    ```
    ./adb sideload crDroidAndroid-14.0-xxx.zip
    ```

  - After a successful sideload, the computer will show the process stopping at 47%, and on the phone you'll be prompted to reboot to recovery again in order to continue flashing Addons (like Google Apps or microG, since those are not built into crDroid). Choose "Yes" to reboot into recovery (and the **adb sideload** process on the computer will complete at 47%, possibly with an error message about "no error". Yeah. It's normal, roll with it).

If you encounter any other installation errors when sideloading besides ROM zip sideloading stopping at 47%, run **./adb pull /tmp/recovery.log** in terminal to get logs to share while asking for help.

15. If you want to run with Google Apps or microG since we don't ship them built-in, now is the time to install. On the phone, navigate to **Apply update -> Apply from ADB** again, and from the terminal window on your computer, run the following (substituting the actual zip file name):

    ```
    ./adb sideload <Google Apps package>.zip
    ```

16. Since this is a clean install, choose the **Factory reset** option, and choose a filesystem format for the userdata partition (ext4 is old reliable, f2fs may provide a very slight performance advantage).

17. Choose **Reboot system now**

### Update installation steps:

** Option 1: From OTA Updater **

1. Open **Settings > System > Updater** on the phone. Before loading an update to install, choose **Preferences** from the menu and turn on the **Prioritize update process** and **Delete updates when installed** toggles. Now either check for updates, or choose **Local update** from the menu & select the desired ROM zip file from your phone's internal storage.

2. Once it has finished verifying the update, choose **Continue** to begin installation.

_Protip: Enable "Stay awake while charging" in Developer Options, or use the "Caffeine" QS tile to keep the screen on, or just set the Display timeout to 10 minutes to cut the installation time from 2 hours down to less than 10 minutes. It slows down drastically if the screen goes off._

** Option 2: From Recovery **

1. Make sure you have the *same Google Apps or microG installation zips* (or updated versions of the same Android version/architecture) as when you did the initial clean installation available to sideload. If you change to different GApps now, things will get broken.

2. Reboot phone to recovery and connect USB cable to computer once you're in the crDroid recovery environment. Open a terminal on the computer and run **adb devices** to verify that the phone is visible to the computer.

3. On the phone, choose **Apply update -> Apply from ADB** to begin the phone listening for an update. On the computer, run **adb sideload path/to/crdroid.zip** (substituting the correct path & filename).

4. On the computer, the process will freeze at 47%, and on the phone you'll see it's prompting you to reboot to recovery to install addons (like Google Apps). Choose "Yes" on the phone to reboot to recovery now, and notice that the **adb sideload** process has finished on the computer with an error message about "no error". This is "normal". _Thanks, Google!_

5. If you have any addons to flash (Google Apps, microG, custom kernel zips, etc) now is the time to **adb sideload** them. On the phone, choose **Apply update -> Apply from ADB** to start the phone listening, and then run **adb sideload path/to/installation.zip** from the computer for each thing you need to install. *Recovery does not process addon.d OTA survival scripts like the booted OTA updater in Settings does, so you canNOT skip installing the Google Apps zip now if you previously had them installed, or it will ruin your current installation if you reboot without them.*

6. On the phone, choose **Reboot system now**.
