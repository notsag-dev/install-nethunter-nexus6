# nethunter-nexus6
1) Enable developer options
2) Enable USB debugging and OEM unlocking
3) Download Android platform tools (cli tools) on your computer (this includes `adb` and `fastboot` binaries)
4) Enter bootloader/fastboot mode (power + vol down)
5) Run `fastboot flashing unlock` and `fastboot oem unlock`
6) Download twrp recovery for Nexus 6
7) Enter bootloader
8) fastboot flash recovery _twrpfile_
9) Enter recovery mode
10) adb push _magisk_ /
11) From twrp install magisk
12) Boot into the phone and check root with rootchecker
13) Then go to bootloader again, enter twrp, copy nethunter zip to `/` using `adb push`
14) Install nethunter from twrp
15) Boot phone and run Nethunter app to complete installation


Troubleshooting tips:
- After running flash-all of the Android recovery image _image-shamu-n6f27m_ the filesystem broke for me. From twrp it's impossible to even wipe anything. The solution is to change the /data filesystem to fat and then back to ext4.
