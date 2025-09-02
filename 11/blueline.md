GApps are **NOT** supported! The Pixel 3's partitions are too small to store both crDroid and GApps. Installing GApps will result in your phone bootlooping, and support will not be provided if you attempt to install them.

### Pre-installation:
You will need to have a computer with the Android Platform Tools installed. See XDA's guide for installing the platform tools: https://www.xda-developers.com/install-adb-windows-macos-linux/

### Unlocking bootloader:
Warning! This will wipe your phone. Back up before continuing.

To install crDroid, you'll need to unlock your bootloader. Open the Settings app, then go to About phone, and tap on "build number" until it says "You are now a developer!" or prompts you to enter your passcode. Afterwards, go to System > Advanced > Developer Options in Settings, then enable the options "USB Debugging" and "OEM Unlock". If the "OEM Unlock" option is not present or greyed out, your phone was likely purchased from a carrier that restricts bootloader unlocking (e.g. Verizon, AT&T, Docomo) and you cannot continue. Connect the phone to your computer and run "adb reboot bootloader", you will get a prompt asking if you'd like to trust the computer, say yes. When your phone enters Fastboot mode, run "fastboot flashing unlock" on your computer and select continue on the screen.

### Installing recovery
Get the latest dtbo.img and boot.img from the Recovery section on the download page. Run "fastboot flash boot /path/to/boot.img" and once that finishes, "fastboot flash dtbo /path/to/dtbo.img". Now press volume up until you see "Recovery Mode", then press power.

### Installing crDroid from recovery
Download the crDroid ZIP file.  
Select "Factory Reset", then "Format data / factory reset".  
Once formatted, go back to the main menu, select "Apply Update", then "Apply from ADB".  
Connect the Pixel to your computer via USB, and then on your computer, run `adb sideload path/to/crdroid.zip.
