### Pre-installation:
You will need to mod your Nintendo Switch. The [NH Switch Guide](https://nh-server.github.io/switch-guide/) works well for v1 switches.  
You will have to make physical modifications to your Switch if it is a v2, Lite, or OLED.  
It is recommended to be running the latest [Hekate](https://github.com/CTCaer/hekate/releases/latest). For Android 14, you **must** be running at least Hekate 6.1.0.  
You can optionally install [Magisk](https://github.com/topjohnwu/Magisk/releases/latest) or GApps.  
You will need a MicroSD card that is at least 16GB. This guide does not cover eMMC installation due to the risk of bricking the Switch.  

### SD Card preparation:
You will need to download all files from the [recovery folder on SourceForge](https://sourceforge.net/projects/crdroid/files/nx_tab/10.x/recovery/) and copy them to the following directories on your MicroSD card. Create the directories if they do not exist.  
You can mount your SD card from Hekate by selecting "Tools", then "USB Tools", "SD Card", then "USB Mass Storage".
- switchroot/install/boot.img
- switchroot/install/recovery.img
- switchroot/install/nx-plat.dtimg
- switchroot/android/bl31.bin
- switchroot/android/bl33.bin
- switchroot/android/bootlogo_android.bmp
- switchroot/android/icon_android_hue.bmp
- switchroot/android/boot.scr
- bootloader/ini/android.ini

You can now eject your SD Card and go back to Hekate. In Hekate, select "Nyx Settings", then "Dump Joy-Con BT".  
When it succeeds, press OK.  

### Partitioning:
Any data on your MicroSD card will be deleted. Back it up to avoid data loss. 
Boot into Hekate, select "Tools", then "Partition SD Card", then press "OK".  
Make your partition scheme based on your needs.  
Make sure to give Androd at least 10GB.  
If prompted, select "Dyanmic: Android 13+".  
Press "Next Step", then "Start".  
When the process is complete, press "Flash Android" and reboot to recovery.

### Installing crDroid from recovery
Download the crDroid ZIP file.  
Select "Factory Reset", then "Format data / factory reset".  
Once formatted, go back to the main menu, select "Apply Update", then "Apply from ADB".  
Connect the switch to your computer via USB, and then on your computer, run `adb sideload [path to crdroid.zip].
