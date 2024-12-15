### Pre-installation:

* **Device oem unlocked**
* Firmware (from download page, firmware button)
* Recovery (from download page, recovery button)
* Optional gapps (from download page, gapps button)
* Optional KernelSU apk (get it on [release page](https://github.com/tiann/KernelSU/releases) from their GitHub - click "show all assets" to see the apk)

### First time installation (clean flash):
* Backup your data to PC, OTG flash drive
* Boot to fastboot (volume down + power button)

#### Flashing boot:

```
fastboot flash boot /path/to/boot.img
```

#### Boot to Crdroid recovery:

```
fastboot reboot recovery
```

#### Flashing crDroid:
* Select "Apply update" -> "Apply from ADB"
* Connect your phone to PC
* Now sideload crDroid zip

```
adb sideload /path/to/crDroid.zip
```
* Select "no" on the prompt that comes after sideloading crDroid.zip

#### Format data:
* Select "Factory reset" -> "Format data/factory reset"

#### Flashing Firmware:
* Select "Apply update" -> "Apply from ADB"
* Now sideload Firmware zip

```
adb sideload /path/to/firmware.zip
```

#### Flashing gapps(Optional):
* Select "Apply update" -> "Apply from ADB"
* Now sideload Gapps zip

```
adb sideload /path/to/gapps.zip
```

#### Reboot to system:
* Select "Reboot system now"

### Update installation (dirty flash):
#### Updater firmware(Optional):
* Go to Settings -> System -> System updaters -> Show changelog
* Check if the required firmware in the changelog has changed. If there are updates, please update them using the following method. If not, please skip this step
* Reboot to Crdroid recovery
* Select "Apply update" -> "Apply from ADB"
* Now sideload Firmware zip

```
adb sideload /path/to/firmware.zip
```
* Select "Reboot system now"

#### Via Recovery:
* Boot to Crdroid recovery (volume up + power button)
* Select "Apply update" -> "Apply from ADB"
* Connect your phone to PC
* Now sideload crDroid zip

```
adb sideload /path/to/crDroid.zip
```
* Select "no" on the prompt that comes after sideloading crDroid.zip

##### Flashing Gapps(Optional):
* Select "Apply update" -> "Apply from ADB"
* Now sideload Gapps zip

```
adb sideload /path/to/gapps.zip
```

##### Reboot to system:
* Select "Reboot system now"

#### Via OTA:
* Go to Settings -> System -> System updaters -> Download latest build
* Choose install and let it complete, reboot
