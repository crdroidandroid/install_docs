### Pre-installation:
* Gapps linked on download page
* Recovery linked on download page

### Fisrt time installation
### Installing recovery 
* You need to have [Odin](https://drive.google.com/file/d/1-tk7QBvxc8ixuU7XrGiGmNAjqspaliLv/view?usp=drive_link) in your PC
* Now go to Downloads and unzip it. 
* Open the folder and execute Odin3_v3.14.4.exe
* It will open the Odin
* Power OFF device
* Reboot phone in Download Mode (1st plug-in USB-cable to your Note10+!!!), push Volume Up + Volume Down buttons, while pushing them plug-in USB-cable to PC
* In Odin, flash d2s-recovery.rar in any slot
* Hold volume down + power until screen goes black, then hold volume up + power until you see recovery screen, all while phone is connected to computer.
* Now you are booted to recovery

## Installing via recovery
**Note: Please go through the installing recovery once**
* Backup your data to PC, OTG flash drive.
* Now navigate to ***FACTORY RESET***
* Select: ***Format data/factory reset***
* After wiping go back and navigate to ***Apply update***
* Select  ***Apply from adb***
* On PC terminal type
* Now install crDroid zip via sideload with

```
adb sideload [drag-and-drop-the-zip-in-terminal]
```
* Reboot to recovery
* Flash gapps with

```
adb sideload [drag-and-drop-the-gapps-in-terminal]
```
* Reboot and enjoy !!!

### Update installation:
## 1. Using recovery
* Boot to recovery (Hold Pow + Vol Up)
* Download the the update zip in the external sdcard of the device or otg
* Choose install 
* Select the crDroid.zip and gapps (if the phone has gapps before update)
* Reboot and enjoy !!!

## 2. Using ADB Sideload on recovery 
* Boot to recovery (Hold Pow + Vol Up)
* Open Terminal in your pc (in the the platform tools folder)
* Type:

```
adb devices
```
* It will show your and device code and mode type
* Now head to the recovery: ***Apply Update > Update Via ADB***
* Now type (in terminal):

```
adb sideload [drag-and-drop-in-terminal-cr.zip]
```

* Flash gapps
```
adb sideload [drag-and-drop-in-terminal-gapps.zip]
```
* Reboot and enjoy !!!

## 3. Update via OTA
* Go to Settings -> System -> Updater and download latest build
* Choose install and let it finish
* If having gapps, reboot to recovery and sideload gapps package again
* Reboot
