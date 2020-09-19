# nethunter-nexus6
Step-by-step guide to install Kali Nethunter on Nexus 6 (Shamu), because I won't spend that entire day trying to do this ever again 😭😆.

1) Enable developer mode by repeatedly tapping on the build number from `settings > about phone > build number`.
2) Enable USB debugging and OEM unlocking.
3) Download and install Android Studio.
4) Download Android platform tools (this includes `adb` and `fastboot` binaries). Add to PATH.
5) From Android Studio go to _tools > SDK manager_. Then install the SDK corresponding to the Android version of the phone.
6) Plug the phone to the computer and grant permissions for USB debugging on the phone.
7) Check if USB debugging is OK by running `adb devices` on the computer. The device should be listed.
8) Enter bootloader/fastboot mode on the phone by pressing power button + vol down (hold for several seconds).
9) Run `fastboot flashing unlock` and `fastboot oem unlock` from your computer.
10) Download twrp recovery for Nexus 6. I downloaded the version 3.3.1 from https://dl.twrp.me/shamu/ (there's also the version 3.4.0 which did not work for me). For other devices check the [devices page](https://twrp.me/Devices/).
11) Restart bootloader on the phone.
12) Run `fastboot flash recovery twrp-3.3.1-0-shamu.img` from the computer.
13) Download the Magisk zip (this is the app that roots the phone). I downloaded the version 20.4 from the [Magisk's Github page](https://github.com/topjohnwu/Magisk/releases/tag/v20.4).
15) Run `adb push Magisk-v20.4.zip /` on the computer.
13) Enter recovery mode from the phone (accessible from the bootloader). It should enter the twrp recovery mode.
15)  the twrp recovery menu install magisk
16) Boot into the phone and check root with rootchecker
17) Then go to bootloader again, enter twrp, copy nethunter zip to `/` using `adb push`
18) Install nethunter from twrp
19) Boot phone and run Nethunter app to complete installation

Troubleshooting tips:
- After running flash-all of the Android recovery image _image-shamu-n6f27m_ the filesystem broke for me. From twrp it's impossible to even wipe anything. The solution is to change the /data filesystem to fat and then back to ext4.
