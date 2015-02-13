
    
  <div id="readme" class="blob instapaper_body">
    <article class="markdown-body entry-content" itemprop="mainContentOfPage"><h1>
<a id="user-content-vanilla-implementation-of-linux-kernel-version-38-for-bbb" class="anchor" href="#vanilla-implementation-of-linux-kernel-version-38-for-bbb" aria-hidden="true"><span class="octicon octicon-link"></span></a>Vanilla implementation of linux kernel version 3.8 for BBB</h1>

<h3>
<a id="user-content-procedure" class="anchor" href="#procedure" aria-hidden="true"><span class="octicon octicon-link"></span></a>Procedure</h3>

<h1>
<a id="user-content-step-1" class="anchor" href="#step-1" aria-hidden="true"><span class="octicon octicon-link"></span></a>Step-1</h1>

<p>Get the tools installed on your system. First of all install the compiler for arm.</p>

<p><code>sudo apt-get install gcc-arm-linux-gnueabi</code></p>

<p><code>sudo apt-get install lzop</code></p>

<h1>
<a id="user-content-step-2" class="anchor" href="#step-2" aria-hidden="true"><span class="octicon octicon-link"></span></a>Step-2</h1>

<p>It will be better for you if you also install U-boot which is an image compressing program. You can do that by:</p>

<p><code>sudo apt-get install u-boot-tools</code></p>

<h1>
<a id="user-content-step-3" class="anchor" href="#step-3" aria-hidden="true"><span class="octicon octicon-link"></span></a>Step-3</h1>

<p>Now download the kernel from github.</p>

<p><code>git clone git://github.com/beagleboard/kernel.git</code></p>

<p><code>cd kernel</code></p>

<p><code>git checkout 3.8</code></p>

<p>Now execute the script patch.sh</p>

<p><code>./patch.sh</code></p>

<p>Some further preperation before the kernel is built:</p>

<p><code>cp configs/beaglebone kernel/arch/arm/configs/beaglebone_defconfig</code></p>

<p>Also download the power management firmware:</p>

<p><code>wget http://arago-project.org/git/projects/?p=am33x-cm3.git\;a=blob_plain\;f=bin/am335x-pm-firmware.bin\;hb=HEAD -O kernel/firmware/am335x-pm-firmware.bin</code></p>

<p><code>cd kernel</code></p>

<p>Please make sure that you are in the proper directory. When you type <code>pwd</code> you should get:
<code>/kernel/kernel/</code> preceeded by your home directory.</p>

<h1>
<a id="user-content-step-4" class="anchor" href="#step-4" aria-hidden="true"><span class="octicon octicon-link"></span></a>Step-4</h1>

<p><code>make ARCH=arm CROSS_COMPILE=arm-linux-gnueabi- beaglebone_defconfig</code></p>

<p><code>make ARCH=arm CROSS_COMPILE=arm-linux-gnueabi- uImage dtbs</code></p>

<p><code>make ARCH=arm CROSS_COMPILE=arm-linux-gnueabi- uImage-dtb.am335x-boneblack</code></p>

<p><code>make ARCH=arm CROSS_COMPILE=arm-linux-gnueabi- modules</code></p>

<p>The whole process might take about 30 minutes. But in some cases it might take more.</p>

<h1>
<a id="user-content-step-5" class="anchor" href="#step-5" aria-hidden="true"><span class="octicon octicon-link"></span></a>Step-5</h1>

<p>Finally in the folder <code>/kernel/kernel/arch/arm/boot/</code> you will find your zimage file.</p>
</article>
  </div>

  </div>
</div>

      

  </body>
</html>
