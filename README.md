DESCRIPTION   
A collection of notes/instructions to get [openFrameworks](http://openframeworks.cc/) to run on the [Udoo Quad](http://elinux.org/UDOO#UDOO_Quad). There are no real files here.      

REQUIREMENTS
- Udoo Quad
- 4GB Micro SD card

INSTRUCTIONS   
- Download the 3GB disk image  

http://www.jvcref.com/files/UDOO/udoo_jessie_xfce_OF_SHRUNK.img

- Use dd to write to an SD card.  This is similar but not exact to [these instructions](http://xmodulo.com/2013/11/write-raspberry-pi-image-sd-card.html). Be careful.

`$ sudo dd if=udoo_jessie_xfce_OF_SHRUNK.img of=/dev/REPLACE_THIS_WITH_SD_CARD_OR_SUFFER bs=1M`

`gparted` is installed on the system if you want to resize the partition to fill the disk. This may be easier on a seperate system (not the UDOO)

DISK CONTENTS   
- Networking enabled [via wired connection](http://www.udoo.org/forum/debian-jessie-rootfs-with-gpu-vpu-t693-10.html?sid=d8734726d01107fc4cad534d9e83d242#p5934)
- SSH enabled (primarily how I have been working)
- OF is in /home/debian/openFrameworks
- test apps are openFrameworks/apps/udooApps
- Autologin is enabled via lightdm
- SMB/Avahi is enabled and provides access to the root filesystem. On a Mac I mount via `smb://udoo.local`. It should also show up as udoo_samba in a network browser.  
- simple non-OF app in `home/debian/TEMP/hello` Use compile.sh to compile. This was used to initially get a window open and OpenGL working
- `export DISPLAY=:0` set in `.profile` so you can run apps over ssh on login

LOGIN INFO:   
user: debian   
pass: debian   

`$ ssh debian@udoo.local`   

NOTES:   
I just started with the [OF 0.8.1 Arm7 downloadable](http://www.openframeworks.cc/versions/v0.8.1/of_v0.8.1_linuxarmv7l_release.tar.gz) and mostly hacked on

openFrameworks/libs/openFrameworksCompiled/project/linuxarmv7l/config.linuxarmv7l.default.mk
openFrameworks/libs/openFrameworksCompiled/project/makefileCommon/config.shared.mk

I also poked around and likely changed these files but it may not have been necessary

openFrameworks/libs/openFrameworks/utils/ofConstants.h   
openFrameworks/libs/openFrameworks/app/ofAppEGLWindow.cpp   
openFrameworks/libs/openFrameworks/app/ofAppRunner.h   

The base image was provided via [this thread](http://www.udoo.org/forum/debian-jessie-rootfs-with-gpu-vpu-t693.html)






