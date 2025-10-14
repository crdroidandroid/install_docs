### Pre-installation:

* Make sure you have latest firmware available for your country.
* Gapps package (optional) (from download page, gapps button)
* Use only HyperOS 2.0.202+ fw.
### First time installation (clean flash):

* Flash the provided images via fastboot using "fastboot flash boot boot.img flash init_boot init_boot.img flash dtbo dtbo.img flash recovery recovery.img flash vendor_boot vendor_boot.img"
* Reboot to recovery using either volume + and power button combo or via fastboot command
* Navigate to Apply Update  > Apply from ADB
* adb sideload the crdroid zip using "adb sideload crdroid-*-peridot.zip"
* Reboot recovey
* Install gapps (optional)
* Factory reset/format data
* Reboot system

```
adb sideload crDroid.zip
```
* When asked to sideload gapps, choose 'Yes' to reboot to recovery or 'No' if you don't want gapps and want to reboot to system
* Now if you choosed to install gapps, simply sideload gapps.zip the same way you installed crDroid.zip then reboot to system

### Update installation:
#### Via recovery (recommended way):
* Boot to recovery
* Choose rom.zip
* Reinstall gapps (if you have before)

#### Via OTA:
* Go to Settings -> System -> Updater and download latest build
* Choose install and let it finish
* If having gapps, reboot to recovery and reinstall gapps package again
* Reboot

