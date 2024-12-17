### Pre-installation:

* Recovery (from download page, Recovery button)
* Rom (from download page)
* GApps (optional) (from download page, gapps button)
* Firmware (from download page, Firmware button)

### First time installation (clean flash):

* Backup your data to PC, OTG flash drive
* Boot to fastboot and flash recovery

```
fastboot flash  recovery_a recovery.img
fastboot flash  recovery_b recovery.img
```
* Now boot to  by holding VOL UP + POWER
* Format Data
* Flash Firmware (Optional, flash if not on latest Firmware)
* Flash the crDroid (Ignore system mount error)
* Reboot to recovery and then flash GApps
* Factory Reset (Format data is recommended)
* Reboot to system

### Update installation:

#### Via OTA [recommended way):

* Go to Settings -> System -> Updater and download latest build
* Choose install and let it finish
* Reboot

#### Via recovery:
* Boot to recovery
* Flash the update
* Wipe dalvik, cache
* Reboot and Enjoy
