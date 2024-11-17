### Required Files

- Download the LineageOS copy-partitions script from **[here](https://mirrorbits.lineageos.org/tools/copy-partitions-20220613-signed.zip)**

- Download the needed files for you device from here **[here](https://sourceforge.net/projects/crdroid/files/channel/10.x/)**

- Required device files for first-time retrofit dynamic partitions conversion:
  - boot.img
  - dtbo.img
  - super_empty.img
  - ...and then the latest OTA zip for you device (crDroidAndroid-14.0-xxx.zip)

  *_Do \*\*\*NOT\*\*\* substitute \*any\* of these files with files that you've downloaded elsewhere if you want support for your installation._*

### First time installation (clean flash):

1. **Prepare the device for Fastboot mode:**
   - Power off the device.
   - Press and hold **Power** + **Volume Down** buttons until Fastboot mode appears.

2. **Connect the device to your PC** via USB cable and verify the connection with:
   fastboot devices

3. **Wipe the "super" partition:**  
   fastboot wipe-super super_empty.img

4. **Flash the required images:**
   - Boot image:  
     fastboot flash boot boot.img
   - Dtbo image:  
     fastboot flash dtbo dtbo.img

5. **Enter Recovery mode:**
   - Use the volume buttons to navigate to "Recovery Mode."
   - Press the Power button to confirm.

6. **Perform a Factory Reset in Recovery mode:**  
   - Navigate to **"Wipe data/factory reset"**.  
   - Confirm the action to clear old data.

7. **Install the ROM:**
   - Use the adb sideload command with the ROM file:  
     adb sideload crDroidAndroid-14.0-xxx.zip

### Update installation:

1. **Reboot the device into Recovery mode.**

2. **Wipe cache/dalvik (optional but recommended).**  
   - Find and confirm the **"Wipe cache/dalvik"** option.

3. **Install the update ROM:**
   - Use the adb sideload command to flash the update file:  
     adb sideload crDroidAndroid-14.0-xxx.zip

4. **Reboot the device:**  
   - After installation, select **"Reboot system now"** from the Recovery menu.
 
 #### Via OTA:
* Go to Settings -> System -> Updater and download latest build
* Choose install and let it finish
* Reboot

Your device should now be updated!
