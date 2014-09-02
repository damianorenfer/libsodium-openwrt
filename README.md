libsodium-openwrt
=================

You find this package in the new OpenWrt feed : [libs/libsodium](https://github.com/openwrt/packages/tree/master/libs/libsodium)

##Deprecated

[libsodium](https://github.com/jedisct1/libsodium) OpenWrt Makefile for package building (dynamic lib)

###Build for your platform

1. Install the OpenWrt environnement : http://wiki.openwrt.org/doc/howto/buildroot.exigence
2. Use the Makefile of this repo to build your libsodium package. Example : http://wiki.openwrt.org/doc/devel/packages
3. From the buildroot dir : `make package/libsodium/{clean,prepare,configure,compile} V=s`

###Installation

1. Upload the libsodium_0.4.5-1_{PLATFORM}.ipk to your OpenWrt router : `scp libsodium_0.4.5-1_{PLATFORM}.ipk.ipk root@ip_of_your_openwrt:~`
2. Now remote login to your OpenWrt : `ssh root@ip_of_your_openwrt`
3. Remote install the package : `opkg install libsodium_0.4.5-1_{PLATFORM}.ipk`
