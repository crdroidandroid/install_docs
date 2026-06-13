### Before start flashing

- Always have backup of your internal storage
- Use recovery meant for Android 16 (download page, recovery button)
- To retain recovery after rom flash, don't forget to tick the option "Automatically Reflash recovery after flashing a rom" in recovery. Else recovery will be replaced by recovery from rom
- For KernelSU Managers Refer [here](https://gist.github.com/Chaitanyakm/fdb91e6602ce104f92ae68d70c18d7c9)
- Gapps (download page, gapps button)
- Only Hos3 fw is compatible download from -: [here](https://xmfirmwareupdater.com/firmware/marble/)

### Clean flash:
- Download the ROM,Firmware and Gapps package from nikgapps
- Boot into recovery
- Flash HOS3 Firmware
- Wipe Dalvik/Art Cache,cache, FRP, metadata 
- Flash the ROM(tick clean payload flash) and reboot to recovery
- Flash the Nikgapps
- Tap on format data, type yes and reboot to system

### Dirty flash:
- Download the ROM and Gapps package from nikgapps
- Boot into recovery
- Flash the ROM(tick clean payload flash) and reboot to recovery
- Flash the Nikgapps
- Wipe Dalvik/ArtCache and Cache
- Reboot To System
