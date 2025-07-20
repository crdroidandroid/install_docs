## Before you install
* Unlock your bootloader. Instructions for that can be found on the web, but generally you have to downgrade to OxygenOS 11 and then unlock.
* This ROM **requires** you to be on OxygenOS 12, preferably the latest, before starting to install, unless you are coming from another ROM and had OxygenOS 12 installed when you installed the ROM you're coming from.
* The Google apps package that's recommended is on the install page. I, however, use microG, so I cannot assist with gapps related issues (such as Play Integrity) unless it is device specific. **Most users should use Nikgapps, the one linked on the page. microG also fully works, and no google apps also fully works.**

## Clean flash (First time installation)
* Backup your data
* Make sure you are on OxygenOS 12; it is a prerequisite
* Factory reset from recovery, then **choose Apply Update and choose Apply from ADB**. Now, on your computer, use

```
adb sideload crDroid.zip
```
* It will reach 47% and then ask you if you wish to reboot to recovery to install additional packages. **If you wish to install NikGapps, choose Yes. Otherwise, choose No and reboot to system.**
* You are done!

## Updating
### Through recovery (*recommended*)
* Boot to recovery
* Choose Apply Update, and Apply from ADB.
* On your computer, use this to install the update:

```
adb sideload crDroid.zip
```
* It will reach 47% and ask if you wish to install additional packages. If you had Gapps, choose Yes to reboot to recovery, sideload your GApps package, and reboot. Otherwise, choose No.

## Via OTA
* Go to Settings -> System -> System updates and download the latest update.
* Choose install and let it finish updating.
* **If you had GApps, reboot to recovery and sideload your GApps package again.**
* Reboot
