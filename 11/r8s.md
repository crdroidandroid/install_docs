### Pre-installation:

 * You must have Android 13 OneUI 5/5.1 before the install
* Recovery (from download page, recovery button)
* Optional gapps (from download page, gapps button)
* Odin3 [Download](https://undocumented.software/Odin_3.13.1.zip)


### First time installation (clean flash):

* Remove all Google accounts from your device to avoid FRP (Factory reset protection).
* Backup Data if needed.
* Power off the phone, then enter Download Mode using Volume Down + Volume Up and enter Odin3.
* In Odin3, select any (TWRP, or provided recovery file) in the AP slot, then disable auto-reboot in Odin3 settings, then click start.
* After the flash is done, hold Volume Down + Power until it reboots, then Volume Up + Power until in recovery.
* In crDroid recovery, select Factory reset, then Format data/factory reset.
* After it's done, click on advanced, then reboot recovery.
* Back in recovery, click Apply Update, then Apply from ADB.
* Then put this command on your PC to install the crDroid rom:

```
adb sideload crdroid.zip
```
* After it's done, do the same steps to install any additional packages.
* Reboot and enjoy.

### Update installation:

* Go to the system updater in the Settings app, and download the new update.
* After the download is done, the update will be done automatically. 
* Reboot.

NOTE: If after OTA, some additional packages you had installed (e.g Magisk) are not there anymore, reflash them in recovery with ADB.