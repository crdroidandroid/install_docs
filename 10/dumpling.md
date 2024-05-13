### Pre-installation:

* **OOS 10.1 firmware is required**
* Optional gapps (from download page, gapps button)

### First time installation (clean flash):

* Backup your data to PC, OTG flash drive
* Make sure you are on latest OOS 10 or at least OOS 10 firmware installed
* Enter recovery
* flash the rom zip
* flash gapps ( optional )
* Now in recovery go to factory reset and confirm the reset
* Reboot to system

```
adb sideload crDroid.zip
```
* Go back to main menu and reboot to recovery to install gapps (if you don't want gapps, reboot to system)
* To install gapps, simply sideload gapps.zip the same way you installed crDroid.zip then reboot to system

### Update installation:
#### Via recovery (recommended way):
* Boot to recovery
* Choose apply update and Apply from ADB
* Now install crDroid zip via sideload and reboot

```
adb sideload crDroid.zip
```
* If you had gapps, reboot to recovery and sideload gapps.zip and reboot

#### Via OTA:
* Go to Settings -> System -> Updater and download latest build
* Choose install and let it finish
* If having gapps, reboot to recovery and sideload gapps package again
* Reboot
