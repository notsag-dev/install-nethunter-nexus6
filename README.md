# nethunter-nexus6

- Unlock OEM from inside android device
- Download and add to path Android platform tools.
- Download twrp recovery for Nexus 6
- Enter bootloader
- fastboot flash recovery _twrpfile_
- Enter recovery mode
- adb push _magisk_ /
- From twrp install magisk
- Boot into the phone and check root with rootchecker
- Then go to bootloader again, enter twrp, copy nethunter zip to `/` using `adb push`
- Install nethunter from twrp
- Boot phone and run Nethunter app


Note: After running flash-all of the Android recovery image _image-shamu-n6f27m_ the filesystem breaks. From twrp it's impossible to even wipe anything. The solution is to change the /data filesystem to fat and then back to ext4.
