## Pre-installation
* HyperOS latest stable Global firmware is required. As of now: Global OS3.0.x
* Optional GApps (available from the download page)

## First time installation (clean flash)
* Download all required files from the official recovery folder.
* Power off the device and boot into Fastboot mode:
  * Hold Volume Down + Power until FASTBOOT appears on the screen.
    
 ## Flash the required images:
  * fastboot flash boot boot.img
  * fastboot flash dtbo dtbo.img
  * fastboot flash init_boot init_boot.img
  * fastboot flash vendor_boot vendor_boot.img
  * fastboot flash recovery recovery.img
 
## Reboot into recovery:
  * fastboot reboot recovery
* If the device does not boot into recovery automatically:
  * Power off the device.
  * Hold Volume Up + Power until the MI logo appears, then release.

> Note: Touch input works in recovery on most devices. If touch does not work, use the Volume keys to navigate and the Power button to select options.

## In recovery, select:
  * Factory Reset
  * Format data / factory reset
  * Confirm the formatting process.

> This removes encryption, wipes internal storage, and formats the cache partition (if present).

## Return to the main menu and navigate to:
  * Apply Update
  * Apply from ADB
* Sideload the ROM:
  * adb sideload crDroid-*-onyx.zip

> Note: The sideload process may stop at around 47% on the host computer. This is expected behavior and not a failure.

## Reboot to system.
* If you want to use your own Google Apps package (NikGApps recommended):
  * Reboot back into recovery after ROM installation.
  * Sideload the GApps package.
  * Reboot to system.

## Update installation

### Via recovery (recommended way)
* Boot to recovery.
* Navigate to Apply Update -> Apply from ADB.
* Install the latest crDroid build:
  * adb sideload crDroid.zip
* If you use GApps, reboot back into recovery and sideload the GApps package.
* Reboot to system.

### Via OTA
* Go to Settings -> System -> Updater.
* Download the latest build.
* Select Install and wait for the process to finish.
* Reboot.

## Notes
* Do not flash firmware separately. The required firmware components are already included in the ROM package.
* Before reporting installation issues, ensure that all steps above were followed exactly as documented.
* 
