### Pre-installation:

* Boot image (from download page)
* Gapps package (optional) (from download page, gapps button)

### First time installation (clean flash):

* Reboot in recovery
* Format data
* Install rom using adb sideload

```
adb sideload crDroid-Rom.zip
```
* When asked to reboot to recovery, choose 'Yes' if you want to install gapps or 'No' if you don't want gapps and want to reboot to system
* Now if you choosed to install gapps, simply sideload crDroid-gapps.zip the same way you installed crDroid-Rom.zip then reboot to system
* Install gapps (optional) - 

```
adb sideload crDroid-gapps.zip
```
* Start system

### Update installation:
#### Via recovery (recommended way):
* Boot to recovery
* Sideload Rom.zip 

```
adb sideload crDroid-Rom.zip
```
* Reinstall gapps (optional)

```
adb sideload crDroid-gapps.zip
```

#### Via OTA:
* Go to Settings -> System -> Updater and download latest build
* Choose install and let it finish
* If having gapps, reboot to recovery and reinstall gapps package again
* Reboot