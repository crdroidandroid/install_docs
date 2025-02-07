### Pre-installation:
Recovery: Available on the download page (recovery button).  
Gapps: Available on the download page (Gapps button).  
Rom: Available on the download page.  

### First time installation(Clean flash):
* Backup your data before proceeding.
* Boot into **fastboot** by holding VOL DOWN + POWER.
* Flash the recovery using following command:

```
fastboot flash boot boot.img
```

* Now boot to recovery by holding VOL UP + POWER.
* Format Data, even if you are coming from another custom ROM (failure to do this may result in boot issues due to encryption complexities).
* Click Apply update > Apply from ADB.
* If you see the message "Now send the package you want [...]" on console then you can flash ROM via adb sideload:

```
adb sideload crDroid.zip
```

* Wait for the sideload process to complete. When the recovery prompts you to install addons:
   * If you want Gapps, select Yes, then navigate to Apply Update > ADB sideload and sideload Gapps.
   * If you prefer using the vanilla version, select No and reboot to the system.
* Reboot and enjoy.

---

### Update installation:
#### Via recovery (recommended way):
* Boot to recovery.
* Navigate to Apply update and choose from adb sideload.
* Now install crDroid zip via sideload:

```
adb sideload crDroid.zip
```

* Reboot
* If you were using the previous build with Gapps, reapply them using adb sideload. 

**Note**

Updating from crdroid-10.x or any other ROM will require a clean flash. Follow the steps under "First-time Installation" for this scenario.

#### Via OTA:
* Go to Settings -> System -> Updater and download latest build
* Choose install and let it finish
* Reboot
