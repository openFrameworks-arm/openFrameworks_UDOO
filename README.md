No real files here - just a README   


REQUIREMENTS
- Udoo Quad
- 4GB Micro SD Care

INSTRUCTIONS
Download the disk image  

http://www.jvcref.com/files/UDOO/udoo_jessie_xfce_OF_SHRUNK.img

Use dd to write to an SD card

`$sudo dd if=udoo_jessie_xfce_OF_SHRUNK.img of=/dev/REPLACE_THIS_WITH_SD_CARD_OR_SUFFER bs=1M`

`gparted` is installed on the system if you want to resize the partition to fill the disk. This may be easier on a seperate system (not the UDOO)

DISK CONTENTS   

- OF is in /home/debian/openFrameworks
- test apps are openFrameworks/apps/udooApps
- Autologin is enabled via lightdm
- SMB is enabled and provides access to the root filesystem
- simple non-OF app in `home/debian/TEMP/hello` Use compile.sh to compile. This was used to initially get a window open and OpenGL working


LOGIN INFO:   
user: debian   
pass: debian   

NOTES:
I just started with the OF 0.8.1 downloadable and mostly hacked on

openFrameworks/libs/openFrameworksCompiled/project/linuxarmv7l/config.linuxarmv7l.default.mk
openFrameworks/libs/openFrameworksCompiled/project/makefileCommon/config.shared.mk

I also poked around and likely changed these files but it may not have been necessary

openFrameworks/libs/openFrameworks/utils/ofConstants.h
openFrameworks/libs/openFrameworks/app/ofAppEGLWindow.cpp
openFrameworks/libs/openFrameworks/app/ofAppRunner.h




