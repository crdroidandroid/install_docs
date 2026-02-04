### Pre-installation:
* Download the latest ROM file (referred to as **crdroid.zip**).
* Gapps package (optional) (from download page, gapps button)
* Recovery (from download page, recovery button)
* A pc with platform-tools working (adb/fastboot)

### Step 1: Flash recovery:
* Downbload needed file mentioned in pre-installation
* On your pc open your platform-tools's cmd if using (windows) or open terminal on (linux/mac)

 ```
adb -d reboot bootloader
```
or just boot into fastmode via volume down + power button.
* Once you are in fastboot mode check if your device is connected correctly or not by: 

```
fastboot devices
```
* Now install recovery by using:

```
fastboot boot recovery.img
```
***WARNING:***  
*Dont use (fastboot "flash" recovery.img) for installing recovery*
* Use downloaded recovery's image in above command (i am assuming its recovery.img)
* Wipe everything (crdroid.zip must be on your pc)

### Step 2: Installing recovery:
* Reboot into recovery
* Ensure that you have downloaded latest version of rewuired files
* Now go to advanced tab in your recovery and press start_sideload
* Now install crDroid zip via sideload

```
adb sideload crDroid.zip
```
* When rom sideloading is done sideload gapps (optional) same way
* Now if you choosed to install gapps, simply sideload gapps.zip the same way you installed crDroid.zip the reboot into system
* Formate data after sideloading rom ,if it throw error "Cant merge status" go to fastboot mode again then use:
```
fastboot -w
```
* This will erase 'Userdata' or you can simple format through crdroid's recovery

#### Via OTA:
* Go to Settings -> System -> Updater and download latest build
* Choose install and let it finish
* If having gapps, reboot to recovery and sideload gapps package again
* Reboot
