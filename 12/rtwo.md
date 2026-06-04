### Pre-installation
You will need to have a computer with the Android Platform Tools installed. See XDA's guide for installing the platform tools: https://www.xda-developers.com/install-adb-windows-macos-linux/

Verify your phone is running Android 15. If running 14 or earlier, please update to 15 before continuing. 

Verify you have the model number XT2301-4, XT2301-5 or XT2301-1. 

### Unlocking bootloader
To run crDroid, you need to have your bootloader unlocked. Do note that unlocking your bootloader will wipe all your data, please back up your data before continuing. Motorola has their own unique way of unlocking, see Motorola's website at http://motorola-global-portal.custhelp.com/app/standalone/bootloader/unlock-your-device-a to unlock your bootloader. Some Motorola devices may require you to wait up to 7 days after purchasing to allow you to enable OEM Unlocking.

Warning! Some carriers, such as Verizon, AT&T, and Docomo do not allow you to unlock your bootloader. If your phone was purchased from one of these carriers, you **cannot** install crDroid.

### Installing recovery
Get the latest boot.img, dtbo.img, init_boot.img, recovery.img and vendor_boot.img from the Recovery section on the download page. Reboot into Fastboot if you're not in fastboot already, you can do this by running "adb reboot bootloader". Run "fastboot flash boot /path/to/boot.img", then "fastboot flash dtbo /path/to/dtbo.img", then "fastboot flash init_boot /path/to/init_boot.img", then "fastboot flash recovery /path/to/recovery.img", and finally "fastboot flash vendor_boot /path/to/vendor_boot.img" Now press volume up until you see "Recovery Mode", then press power.

### Installing crDroid from recovery
Download the crDroid ZIP file, and GApps if wanted.  
Select "Factory Reset", then "Format data / factory reset".  
Once formatted, go back to the main menu, select "Apply Update", then "Apply from ADB".  
Connect your phone to your computer via USB, and then on your computer, run `adb sideload path/to/crdroid.zip.
When the phone prompts to restart recovery to install addons, say "yes" if installing GApps, then sideload your GApps package when recovery reboots. Otherwise, say no, and reboot your phone.
