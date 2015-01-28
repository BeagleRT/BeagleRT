Vanilla implementation of linux kernel version 3.8 for BBB
============================================================

###Procedure

#Step-1
Get the tools installed on your system. First of all install the compiler for arm.

`sudo apt-get install gcc-arm-linux-gnueabi`

`sudo apt-get install lzop`

#Step-2
It will be better for you if you also install U-boot which is an image compressing program. You can do that by:

`sudo apt-get install u-boot-tools`

#Step-3
Now download the kernel from github.

`git clone git://github.com/beagleboard/kernel.git`

`cd kernel`

`git checkout 3.8`

Now execute the script patch.sh

`./patch.sh`

Some further preperation before the kernel is built:

`cp configs/beaglebone kernel/arch/arm/configs/beaglebone_defconfig`

Also download the power management firmware:

`wget http://arago-project.org/git/projects/?p=am33x-cm3.git\;a=blob_plain\;f=bin/am335x-pm-firmware.bin\;hb=HEAD -O kernel/firmware/am335x-pm-firmware.bin`

`cd kernel`

Please make sure that you are in the proper directory. When you type `pwd` you should get:
`/kernel/kernel/` preceeded by your home directory.

#Step-4

`make ARCH=arm CROSS_COMPILE=arm-linux-gnueabi- beaglebone_defconfig`

`make ARCH=arm CROSS_COMPILE=arm-linux-gnueabi- uImage dtbs`

`make ARCH=arm CROSS_COMPILE=arm-linux-gnueabi- uImage-dtb.am335x-boneblack`

`make ARCH=arm CROSS_COMPILE=arm-linux-gnueabi- modules`

The whole process might take about 30 minutes. But in some cases it might take more.

#Step-5
Finally in the folder `/kernel/kernel/arch/arm/boot/` you will find your zimage file.
