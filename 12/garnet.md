### Pre-installation:

* Make sure you have latest firmware available for your country.
* Gapps package (optional) (from download page, gapps button)

### First time installation (clean flash):

* Flash recovery
* Reboot in recovery
* Format data
* Install last firmware your region
* Reboot recovery
* Install rom.zip
* Reboot recovery 
* Install gapps (optional)
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
* Wipe cache and dalvik

#### Via OTA:
* Go to Settings -> System -> Updater and download latest build
* Choose install and let it finish
* If having gapps, reboot to recovery and reinstall gapps package again
* Reboot
