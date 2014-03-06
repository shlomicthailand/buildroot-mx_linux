buildroot-mx_linux
==================

Updated Buildroot for Amlogic-M3/MX

Note:

This branch will be oriented to products I'm working with.

List of actively maintained devices:

G18REF/MX2REF (mx_linux_g18-mx2_defconfig)

G18REF/MX2REF --NewMTD-- (mx_linux_g18-mx2_newmtd_defconfig)

GO2REFDONGLE (mx_linux_g02refDongle_defconfig) {WIP - No ETA}

STVMX (mx_linux_stvmx_defconfig) {WIP - ETA 2014}

ATV106 (mx_linux_atv106_defconfig) {WIP - No ETA}

G02REF + C150 + Meson 3 + More (TODO)

===================================
This readme was updated: 2013-12-25

How to build
===================================

Get a build host.
You need 32 (i386) bit libraries for the code sorcerer toolchain. One simple way to do this is in an i386 chroot or virtual machine.

Install the build pre-reqs.
In a fresh minimal Debian Unstable install,

% sudo apt-get install git build-essential zip gawk libtool gettext  \
      automake autoconf  nasm unzip gettext flex bison libsdl-image1.2 \
      liblzo2-2 lzma python openjdk-7-jre-headless \
      texinfo libxml-parser-perl wget pkg-config swig cpio zlib1g-dev \
      libncurses5-dev autopoint
Note that as of current (2012-10-10) Debian Unstable, python defaults to python 2.7. Earlier pythons (or python3) will not work.

Set up a key to sign the image
% keytool -genkey -keystore ~/.android/debug.keystore -v -alias \
      androiddebugkey -dname "CN=Android Debug,O=Android,C=US" -keypass \
      android -storepass android -keyalg RSA -keysize 2048 -validity 10000
Build for M1
======================================
% make amlogic_xios-xbmc_defconfig
% make

Build for M3
======================================
% make amlogic_xios_m3-xbmc_defconfig
% make
