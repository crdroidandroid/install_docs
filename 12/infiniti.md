### Pre-installation:

* Optional Google Applications: https://sourceforge.net/projects/nikgapps/files/Elite-Releases/crdroid-official/Android-16/23-Feb-2026/NikGapps-crdroid-official-arm64-16-20260223-signed.zip/download


### First time installation (clean flash):

* Reboot your phone into the bootloader by either restarting it and then when it's off holding down Volume Down and Power or doing adb reboot bootloader
* Flash the Boot Image, the DTBO Image, the Init_boot Image, the Recovery Image, the VBMeta Image, the Vendor_Boot Image
* fastboot flash boot boot.img
* fastboot flash dtbo dtbo.img
* fastboot flash init_boot init_boot.img
* fastboot flash recovery recovery.img
* `fastboot flash vbmeta vbmeta.img`
* `fastboot flash vendor_boot vendor_boot.img`
* Then reboot into recovery by doing `fastboot reboot recovery`
* Once in Recovery Mode, use the Volume Up and Volume Down keys to highlight "Apply update"
* Once "Apply update" is highlighted, select it with the Power Key
* Then do `adb sideload OTAName.zip`
* Once done, it'll prompt you to either choose if you want to restart into Recovery Mode to flash more packages or if you don't want to reboot
* Reboot if you want to flash something like a Google Applications package or don't reboot if you don't want to flash anything else.
* Use the Volume Up and Down Keys to highlight "Factory reset"
* Select "Factory reset' with the Power Key
* Then Select "Format data/Factory Reset"
* Once it asks if you want to format data, choose "YES"
* Once done, it should be automatically highlighted on "Reboot system now" choose that and wait for it to start up!
* Enjoy!

### Update installation:

* Reboot into Recovery Mode by using the Power Menu, `adb reboot recovery`, or by choosing the option in the bootloader with the Volume Keys
* Once in Recovery Mode, use the Volume Up and Volume Down keys to highlight "Apply update"
* Once "Apply update" is highlighted, select it with the Power Key
* Then do `adb sideload OTAName.zip`
* Once done, it'll prompt you to either choose if you want to restart into Recovery Mode to flash more packages or if you don't want to reboot
* If you had Google Applications installed, install them again
* Once done, it should be automatically highlighted on "Reboot system now" choose that and wait for it to start up!
* Enjoy!