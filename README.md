# nethunter-nexus6
Enable developer options
Enable USB debugging and OEM unlocking
Download and install Android Studio
Download Android platform tools (cli tools) to your computer (this includes `adb` and `fastboot` binaries)
From Android studio go to _tools > SDK manager_. Then select the SDK corresponding to your Android version
Plug phone to computer
Check USB debugging is activated by running `adb devices` from your computer. The device should be listed
Enter bootloader/fastboot mode by pressing power button + vol down
Run `fastboot flashing unlock` and `fastboot oem unlock` from your computer
Download twrp recovery for Nexus 6
Enter bootloader
fastboot flash recovery _twrpfile_
Enter recovery mode
adb push _magisk_ /
From twrp install magisk
Boot into the phone and check root with rootchecker
Then go to bootloader again, enter twrp, copy nethunter zip to `/` using `adb push`
Install nethunter from twrp
Boot phone and run Nethunter app to complete installation

Troubleshooting tips:
- After running flash-all of the Android recovery image _image-shamu-n6f27m_ the filesystem broke for me. From twrp it's impossible to even wipe anything. The solution is to change the /data filesystem to fat and then back to ext4.
