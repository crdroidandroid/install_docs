### Pre-installation:
* Download the latest ROM file (referred to as **crdroid.zip**).
* Gapps package (optional) (from download page, gapps button)
* Recovery (from download page, recovery button)
* A pc with platform-tools working (adb/fastboot)

### Step 1: Flash recovery:
* Download needed file mentioned in pre-installation
* On your pc open your platform-tools's cmd if using (windows) or open terminal on (linux/mac)

```
adb -d reboot bootloader
```
or just boot into fastboot mode via volume down + power button.
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
* Ensure that you have downloaded latest version of required files
* Now go to advanced tab in your recovery and press start_sideload
* Now install crDroid zip via sideload

```
adb sideload crDroid*.zip
```
* When rom sideloading is done reboot recovery and sideload gapps (optional) same way
* Format data when everything is done is done (for clean flash) ,if it throw error "Cant merge status" then go to fastboot mode again then use:

```
fastboot -w
```
* This will erase 'Userdata' or you can simple format through crdroid's recovery

#### Via OTA:
* Go to Settings -> System -> Updater and download latest build
* Choose install and let it finish
* If having gapps, reboot to recovery and sideload gapps package again
* Reboot
