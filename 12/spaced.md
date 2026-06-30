### Pre-installation
Before you begin, ensure you have downloaded all the necessary files to your PC:
* **ROM Zip:** The main custom ROM installation file.
* **Firmware & Recovery:** The latest RealmeUI firmware, *boot.img* and *vendor_boot.img*.
* **GApps Package (Optional):** Available via the "GApps" button on the download page.
* **Copy-Partitions:** *copy-partitions-signed.zip* (Required only if you are on firmware *RMX3151export_13.f18* or newer).

### First-Time Installation (Clean Flash)

1. **Boot to Recovery**
   * Connect your phone to your PC and reboot to the bootloader:

     ```
     adb reboot bootloader
     ```
   * Flash the required partition images:

     ```
     fastboot flash boot boot.img
     fastboot flash vendor_boot vendor_boot.img
     ```
   * Reboot into the newly flashed recovery:

     ```
     fastboot reboot recovery
     ```

2. **Format Data**
   * In recovery, select **Format Data** and confirm.

3. **Flash Copy-Partitions *(Conditional)***
   * *Skip this step if you are on older firmware.*
   * Navigate to **Apply Update** -> **Apply from ADB**.
   * Sideload the partitions script:

     ```
     adb sideload copy-partitions-signed.zip
     ```
   * Once completed, **reboot back to recovery** before proceeding.

4. **Flash the ROM**
   * Navigate to **Apply Update** -> **Apply from ADB**.
   * Sideload the ROM zip (this may take a few minutes):

     ```
     adb sideload rom.zip
     ```

5. **Flash GApps *(Optional)***
   * If you want Google Apps, **reboot to recovery** once more.
   * Navigate to **Apply Update** -> **Apply from ADB** and sideload GApps:

     ```
     adb sideload gapps.zip
     ```

6. **Reboot**
   * Select **Reboot System** and enjoy!

### Update Installation (Dirty Flash)

#### Method 1: Via Recovery (Recommended)
1. Reboot your device into recovery mode.
2. Navigate to **Apply Update** -> **Apply from ADB** and sideload the updated ROM:

   ```
   adb sideload rom.zip
   ```
