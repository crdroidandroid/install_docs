### Pre-installation:
You will need to mod your Nintendo Switch. The [NH Switch Guide](https://nh-server.github.io/switch-guide/) supports all Switch models. Do note that unless you have a v1 Switch, you will need to install a modchip. 

It is recommended to be running the latest [Hekate](https://github.com/CTCaer/hekate/releases/latest). For Android 15, you **must** be running at least Hekate 6.1.0.  
You can optionally install [Magisk](https://github.com/topjohnwu/Magisk/releases/latest) or GApps.  
You will need a MicroSD card that is at least 16GB, Samsung SD cards tend to work best with Android. While crDroid does support eMMC installation, it is not covered in this guide as SD Card installation is recommended. You can follow [Switchroot's guide](https://wiki.switchroot.org/wiki/android/14-u-emmc-boot-guide) if you wish to install on the eMMC. Do note you still will need an SD card for Hekate if you're using the eMMC, but the size does not matter if Android is installed on the eMMC, as Hekate is only about 1MB.   

### SD Card preparation:
You will need to download all files from the [recovery folder on SourceForge](https://sourceforge.net/projects/crdroid/files/nx_tab/11.x/recovery/) and copy them to the following directories on your MicroSD card. Create the directories if they do not exist.  
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

### android.ini configuration:
android.ini is the file that Hekate uses to provide boot settings for Android. In most cases, crDroid's default android.ini will work, but there are additonal settings you can configure if you wish.
* `emmc=1` Add this if you're using the eMMC instead of an SD card.
* `usb3_enable=0` By default usb3_enable is set to 1., you may change it to 0 if you're having issues with Wi-Fi or Bluetooth, but note changing it to 0 will break MTP and ADB.
* `ddr200-enable=1` In Hekate, go to "Console Info" -> microSD and check "Max Bus Speed:". If the Max Bus Speed is DDR200, add this flag. DO NOT ADD THIS FLAG IF THE VALUE IS NOT DDR200! Enabling this flag on a non-DDR200 card will likely result in data loss and/or Android becoming corrupted.

### Partitioning:
Any data on your MicroSD card will be deleted. Back it up to avoid data loss. 
Boot into Hekate, select "Tools", then "Partition SD Card", then press "OK".  
Make your partition scheme based on your needs.  
Make sure to give Android at least 10GB.  
If prompted, select "Dyanmic: Android 13+".  
Press "Next Step", then "Start".  
When the process is complete, press "Flash Android" and reboot to recovery.

### Installing crDroid from recovery
Download the crDroid ZIP file.  
Select "Factory Reset", then "Format data / factory reset".  
Once formatted, go back to the main menu, select "Apply Update", then "Apply from ADB".  
Connect the switch to your computer via USB, and then on your computer, run `adb sideload [path to crdroid.zip].
