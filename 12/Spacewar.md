### Pre-installation:

* Make sure you have rom zip and latest NothingOS firmware.
* Gapps package (optional) (from download page, gapps button)

### First time installation (clean flash):

* Go to bootloader (adb reboot bootloader)
* Then flash boot.img and vendor_boot.img (exp: fastboot flash boot boot.img)
* After that reboot to recovery (fastboot reboot recovery)
* Format your data and click ADB Sideload
* Now sideload the rom.zip (adb sideload path/of/file.zip)
* Get a coffie while its installing
* After installation if you want to put gapps then reboot to recovery again and sideload gapps.zip like rom.zip
* After all reboot the system
* And you got it!

### Update installation:
#### Via recovery (recommended way):
* Reboot to recovery
* Sideload rom.zip
* Reinstall gapps (if you have before)
* Wipe cache and reboot to system

#### Via OTA:
* Go to Settings -> System -> Updater and download latest build
* Choose install and let it finish
* If having gapps, reboot to recovery and reinstall gapps package again
* Reboot to system
