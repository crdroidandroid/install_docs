# Install crDroid for Mi 11X Pro (haydn)

### Pre-installation:

* Download the latest ROM file (referred to as **crdroid.zip**).
* GApps package (optional) (from the download page, GApps button).
* Recovery (from the download page, Recovery button).
* A PC with platform-tools working (`adb`/`fastboot`).

### Step 1: Boot recovery:

* Download the required files mentioned in the pre-installation section.
* On your PC, open the platform-tools command prompt (Windows) or terminal (Linux/macOS).

```
adb -d reboot bootloader

```

* Or boot into Fastboot mode manually using Volume Down + Power.

* Once you are in Fastboot mode, check if your device is connected correctly:

```
fastboot devices

```

* Boot the recovery using:

```
fastboot boot recovery.img

```

WARNING:

* Do not use fastboot flash recovery recovery.img.
* Use the recovery image downloaded from the crDroid download page.
* Replace recovery.img with the actual filename if necessary.

### Step 2: Install crDroid:

* Reboot into recovery.
* Make sure you have downloaded the latest required files.
* From recovery, select Apply Update → Apply from ADB.
* Start ADB sideload.
* On your PC, install crDroid using:

```
adb sideload crDroid*.zip

```
* Once the ROM installation is complete, reboot recovery.

### If You Want Gapps

* If you want to install GApps, sideload the GApps package in the same way:

```
adb sideload gapps*.zip

```

* When everything is finished, format data for a clean installation.

* If recovery shows a "Can't merge status" error, reboot into Fastboot mode and run:

```
fastboot -w

```

* This will erase userdata. You can also format data directly from crDroid Recovery.


### Via OTA

* Go to Settings → System → Updater.
* Download the latest build.
* Select Install and let the update finish.
* If you use GApps and they need to be reinstalled, reboot into recovery and sideload the GApps package again.

* Reboot...
