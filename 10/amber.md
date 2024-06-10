### Pre-installation:

* Make sure you're running on HyperOS (any version)) firmware beforehand; other (older) firmwares WILL NOT work. You can download it from [here](https://xmfirmwareupdater.com/firmware/agate/stable/OS1.0.4.0.UKWMIXM).
* Optional gapps (from download page, gapps button)

#### Flashing Firmware:

* Select "Apply update" -> "Apply from ADB"
* Now sideload Firmware zip

```
adb sideload /path/to/firmware.zip
```
### First time installation (clean flash):

* Backup your data to PC, OTG flash drive  
* Download the boot.img and ROM  
*Note*: the boot.img is AOSP recovery  
* Install ROM's recovery using:

```
fastboot flash boot boot.img
```
* Boot into aosp recovery using:

```
fastboot reboot recovery
```
* Wipe data/factory reset  
* Navigate to apply update  
* On your PC with the downloaded ROM, type in the terminal:

```
adb sideload crdroid.zip
```
* The recovery will ask you if you want to install additional packages press NO  
* Reboot and enjoy  

### Update installation:

* Boot to Crdroid recovery (volume up + power button)  
* Select "Apply update" -> "Apply from ADB"  
* Connect your phone to PC  
* Now sideload crDroid zip  

```
adb sideload crdroid.zip
```
* Reboot and enjoy

### Flashing Gapps(Optional):
* Make sure the device booted first before flashing gapps  
* Select "Apply update" -> "Apply from ADB"  
* Now sideload Gapps zip  

### Via OTA:
* Go to Settings -> System -> System updaters -> Download latest build  
* Choose install and let it complete, reboot
