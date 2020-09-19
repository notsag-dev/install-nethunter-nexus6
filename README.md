# nethunter-nexus6
1) Enable developer mode by repeatedly tapping on the build number from `settings > about phone > build number`.
2) Enable USB debugging and OEM unlocking.
3) Download and install Android Studio.
4) Download Android platform tools (this includes `adb` and `fastboot` binaries). Add to PATH.
5) From Android studio go to _tools > SDK manager_. Then install the SDK corresponding to the Android version of the phone.
6) Plug the phone to the computer and grant permissions for USB debugging on the phone.
7) Check if USB debugging is OK by running `adb devices` on the computer. The device should be listed.
8) Enter bootloader/fastboot mode on the phone by pressing power button + vol down (hold for several seconds)
9) Run `fastboot flashing unlock` and `fastboot oem unlock` from your computer.
10) Download twrp recovery for Nexus 6
11) Restart bootloader
12) Run `fastboot flash recovery _twrpfile_`
13) Enter recovery mode
14) adb push _magisk_ /
15) From twrp install magisk
16) Boot into the phone and check root with rootchecker
17) Then go to bootloader again, enter twrp, copy nethunter zip to `/` using `adb push`
18) Install nethunter from twrp
19) Boot phone and run Nethunter app to complete installation

Troubleshooting tips:
- After running flash-all of the Android recovery image _image-shamu-n6f27m_ the filesystem broke for me. From twrp it's impossible to even wipe anything. The solution is to change the /data filesystem to fat and then back to ext4.
