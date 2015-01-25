BeagleRT
========

BeagleRT project aims to assess the real-time limitations and capabilities of the BeagleBone Black. 

Many applications require a certain degree of real-time response. Flying robots or mobile manipulators are just some simple examples of real time systems. This project will analyze, test and compare the different approaches for providing Real-Time responses with the BeagleBone Black development board and the Linux kernel.

### Getting started
To get started, clone this repository and select one of these kernels (starting with vanilla recommended):
- vanilla kernel
- vanilla with PREEMPT option
- PREEMPT_RT patches
- Xenomai patches

Creata a subfolder that represents the kernel selected and compile it for the BeagleBone Black. Upload the kernel in the subfolder and provide a README that describes the process needed to reproduce the compilation.


###References
- https://www.osadl.org/fileadmin/dam/rtlws/12/Brown.pdf
- https://github.com/beaglepilot/beaglepilot
