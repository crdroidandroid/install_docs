### Pre-installation: 
* Make sure you're on HyperOS 2. HyperOS 3 uses a different kernel version, and so it can cause bricks when trying to flash.
* GAPPS package (optional, from download page)

### First time installation (clean flash):
Flash recovery with:

```
fastboot flash vendor_boot vendor_boot.img --slot=all
```
Reboot with

```
fastboot reboot
```
When the Xiaomi logo comes up, hold the up button until you're booted into recovery.
Flash the ROM, this can be either through a SD card with the rom file or ADB sideload.
The recommended method is ADB sideload.
Go to "Apply Update" and choose your method.
For ADB sideload, run this:

```
adb -d sideload crdroid.zip
```
Now, after the build finishes installing, the recovery will ask if you want to reboot to recovery to install add-ons. 
Choose yes if you want to install GAPPS or any other addon, and choose no and reboot to the system if you don't want to.
To flash GAPPS, just go to Apply Update and choose ADB sideload

```
adb -d sideload gapps.zip
```
### Update installation:
#### Via recovery (recommended way):
* Boot to recovery
* Install the update with ADB sideload.
* Reinstall gapps with ADB sideload (if you have GAPPS).
* Reboot

#### Via OTA:
* Go to Settings -> System -> Updater and download latest build
* Choose install and let it finish
* If you have GAPPS, reboot to recovery and reinstall gapps package again
* Reboot
