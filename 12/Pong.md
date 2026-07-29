### Pre-installation:

    Unlocked Bootloader

    Custom Recovery

    Optional GApps 

First time installation (clean flash):

*    Step 1: Boot into Recovery mode (via Fastboot using Volume Down + Power)

*    Step 2: Go to Wipe -> Format Data and type yes to remove internal storage encryption

*    Step 3: Go to Advanced Wipe, select System, Vendor, Cache, and Dalvik / ART Cache, then swipe to wipe
`
Bash

adb sideload crdroid.zip
`
 *   Step 4: Flash your preferred GApps package (if using a Vanilla build)

 *  Step 5: Format data once more if required, then tap Reboot System

Update installation:

 *  Step 1: Reboot your device into Recovery mode

 *  Step 2: Go to Install and select the newer crDroid update zip

 *  Step 3: Wipe Dalvik and Cache partitions

`
Bash

adb sideload crdroid.zip
`
 *  Step 4: Swipe to flash the update package

 *  Step 5: Tap Reboot System to complete the upgrade
