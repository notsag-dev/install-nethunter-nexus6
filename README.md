# nethunter-nexus6
Step-by-step guide to install Kali Nethunter on Nexus 6 (Shamu), because I won't spend that entire day trying to do this ever again 😭😆.

1) Enable developer mode by repeatedly tapping on the phone's build number from `settings > about phone > build number`.
2) Enable USB debugging and OEM unlocking.
3) Download and install Android Studio.
4) Download Android platform tools (this includes `adb` and `fastboot` binaries). Add to PATH.
5) From Android Studio go to _tools > SDK manager_. Then install the SDK corresponding to the Android version of the phone.
6) Plug the phone to the computer and grant permissions for USB debugging on the phone.
7) Check if USB debugging is OK by running `adb devices` on the computer. The mobile device should be listed.
8) Enter the bootloader/fastboot mode on the phone by pressing power button + vol down (hold for several seconds).
9) Run `fastboot flashing unlock` and `fastboot oem unlock` on your computer.
10) Download TWRP (Team Win Recovery Project) for Nexus 6 to the computer. I downloaded the version 3.3.1's zip file from https://dl.twrp.me/shamu/ (there's also a version 3.4.0 which did not work for me). For other devices check the [devices page](https://twrp.me/Devices/).
11) Restart bootloader on the phone.
12) Flash the TWRP recovery by running `fastboot flash recovery twrp-3.3.1-0-shamu.img` on the computer.
13) Download the Magisk zip (this is the app that roots the phone). I downloaded the version 20.4 from the [Magisk's Github page](https://github.com/topjohnwu/Magisk/releases/tag/v20.4).
14) Copy the Magisk zip file to the phone by running `adb push Magisk-v20.4.zip /`.
15) Enter recovery mode on the phone (accessible from the bootloader). It should enter the TWRP recovery mode.
16) Press the _Install_ menu option, look for the just-copied Magisk zip file and complete its install process.
17) Press the menu buttons _Reboot_ and then _System_ to reboot into the phone normally. Install the app _Root Checker_ from the Play Store and verify that the device has root access.
18) Go to the bootloader again and enter the recovery mode.
19) Download Kali Nethunter [here](https://www.offensive-security.com/kali-linux-nethunter-download/). In my case would be _Nexus 6 Nougat_.
20) Copy Kali Nethunter's zip to the phone by running `adb push nethunter-2020.3-shamu-nougat-kalifs-full.zip /`.
19) Install Kali Nethunter from the TWRP recovery using the _Install_ menu option (the same way Magisk was installed).
20) Boot phone and run Nethunter app to complete installation.

Troubleshooting tips:
- After running flash-all of the Android recovery image _image-shamu-n6f27m_ the filesystem broke for me. From twrp it's impossible to even wipe anything. The solution is to change the /data filesystem to fat and then back to ext4.
