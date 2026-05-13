# Pre installation
Make sure your device model number is SM-G980F, SM-G980F/DS, SM-G981B, or SM-B981B/DS. If your device has a different model number, crDroid will *not* work and you will brick your phone.

You will need to have a computer with the Android Platform Tools installed. See XDA's guide for installing the platform tools: https://www.xda-developers.com/install-adb-windows-macos-linux/

Make sure your phone is on One UI 5.1 before continuing. If you are on an older firmware, OTA update to 5.1 or use Heimdall/Odin to flash 5.1.

# Unlocking the bootloader
WARNING!: This will erase all data on your phone. Back up before continuing. This will also trip Knox, breaking certain Samsung features with no way to reverse them.

Connect the phone to Wi-Fi. Open Settings, and go to "About", then tap build number until you get a toast saying "You are now a developer!" or the phone prompts for your passcode. Now go back to the main Settings menu, scroll down, and you should now have an option called "Developer Options". Go to this section, scroll down until you see an option called "OEM unlock" and enable it.

If the "OEM Unlock" option is not present or greyed out, your phone was likely purchased from a carrier that restricts bootloader unlocking (e.g. Verizon, AT&T, Docomo) and you cannot continue.

Once OEM unlock is enabled, power off your phone, then hold down VolUp+VolDown while connecting your device to a PC. Once you see the cyan warning screen, let go of both buttons, then hold down VolUp until the phone says "Unlock Bootloader?", then, let go and press VolUp again to unlock the bootloader.

Let your phone reboot, and skip everything in the setup. Once at the home page, connect the phone to Wi-Fi, re-enable Developer Options, then go back to developer options and verify that OEM Unlock is still enabled.

# Installing Heimdall
Heimdall is an open source tool used to flash images to Samsung devices in Download Mode. Generally, it is recommended to use Heimdall instead of Odin, since it is open source, still actively maintained, and supports macOS and Linux.

Windows: Install UsbDk: https://github.com/daynix/usbdk/releases/latest. Run through the setup wizard. Once setup is finished, download Heimdall here: https://blob.lineageos.org/downloads/heimdall/Heimdall-Windows-v2.2.2-120625.zip. Extract the ZIP, then hold shift while right clicking the folder, and press "Open PowerShell window here" (on older Windows 10 builds, this may appear as "Open PowerShell here" or "Open command window here"). Verify Heimdall is working by typing ".\heimdall.exe version".

Linux: Download Heimdall here: https://blob.lineageos.org/downloads/heimdall/Heimdall-linux-v2.2.2-120625.zip, extract the ZIP and copy Heimdall into a folder that's in $PATH, such as /usr/local/bin. You may also use the heimdall-flash package included in your distro's repositories, however these builds are usually outdated and not recommended. Verify Heimdall is working by opening a terminal and running "heimdall version"

macOS: Download Heimdall here: https://blob.lineageos.org/downloads/heimdall/Heimdall-macOS-v2.2.2-120625.dmg. Open the DMG, and drag Heimdall into the symlink that's in the DMG. Do *not* use brew's heimdall package, this package is outdated and won't work without disabling SIP, and does not work on Apple Silicon Macs. Verify Heimdall is working by opening Terminal and typing "heimdall version".

# Installing recovery
In developer options, enable the option called "USB Debugging". If it asks if you want to trust the connected device, approve it. Run "adb reboot download" (".\adb.exe reboot download" on Windows). The phone will boot to Download Mode. Afterwards, download the recovery image, and run "heimdall flash --RECOVERY [path/to/recovery.img] --no-reboot" (".\heimdall.exe flash --RECOVERY [path\to\recovery.img] --no-reboot" on Windows). Do note it is case sensitive. Once it is finished, hold down Power+VolDown until the phone turns off, the second the phne turns off, let go of VolDown and hold VolUp (continue holding power) until the phone shows the Samsung logo.

### Installing crDroid from recovery
Download the crDroid ZIP file, and GApps if wanted. Select "Factory Reset", then "Format data / factory reset". Once formatted, go back to the main menu, select "Apply Update", then "Apply from ADB". Connect the phone to your computer via USB, and then on your computer, run "adb sideload path/to/crdroid.zip." (".\adb.exe sideload path\to\crdroid.zip" on windows). When the phone prompts to restart recovery to install addons, say "yes" if installing GApps, then sideload your GApps package when recovery reboots. Otherwise, say no, and reboot your phone.
