### Pre-installation:

*  **Realme UI 4 13 - 13.1.0.161(EX01) firmware is required** 
* Optional gapps (from download page, gapps button)
* Optional KernelSU apk (get it on [release page](https://github.com/tiann/KernelSU/releases) from their GitHub - click "show all assets" to see the apk)


### First time installation (clean flash):

* Backup your data to PC, OTG flash drive
* Make sure you are on latest Realme UI 13 or at least Realme UI 13 firmware installed
* Now in recovery go to factory reset and confirm the reset
* Reboot to recovery
* Choose apply update and Apply from ADB
* Now install crDroid zip via sideload

```
adb sideload crdroid.zip
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
* Reboot
