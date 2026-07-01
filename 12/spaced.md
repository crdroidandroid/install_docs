### Pre-installation
Before you begin, ensure you have downloaded all the necessary files to your PC:
* **ROM Zip:** The main custom ROM installation file.
* **Firmware & Recovery:** The latest RealmeUI firmware, *boot.img* and *vendor_boot.img*.
* **GApps Package (Optional):** Available via the "GApps" button on the download page.

### First-Time Installation (Clean Flash)

1. **Boot to Recovery**
   * Connect your phone to your PC and reboot to recovery:

     ```
     adb reboot recovery
     ```

   * Click *Install* and find the rom.zip (crDroidAndroid-16.0-2026****-spaced-v12.11.zip)
   * Swipe to flash the ROM

2. **Format Data**
   * In recovery, select **Format Data** and *swipe* then type *yes*.

3. **Flash GApps *(Optional)***
   * If you want Google Apps, **reboot to recovery** once more.
   * Navigate to **Sideload** and sideload GApps:

     ```
     adb sideload gapps.zip
     ```

6. **Reboot**
   * Select **Reboot System** and enjoy!

#### Method 1: Via Sideload
1. Reboot to recovery

     ```
     adb reboot recovery
     ```
2. Go to *Advanced* section then select *Sideload*>.
3. Connect your phone to pc then open termninal inside platform tools folder.
4. Then command:

     ```
     adb sideload rom.zip
     ```
5. Then format data and *swipe* then type *yes*.
6. Reboot to system and enjoy!
