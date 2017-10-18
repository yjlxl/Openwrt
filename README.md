# Ubuntu 64bit:
sudo apt-get install build-essential subversion libncurses5-dev zlib1g-dev gawk gcc-multilib flex git-core gettext libssl-dev
# 源码地址
* [https://dev.openwrt.org/wiki/GetSource](https://dev.openwrt.org/wiki/GetSource)
* [OpenWrt 资料](https://openwrt.org/)
* [OpenWrt 安装](https://wiki.openwrt.org/doc/howto/obtain.firmware)
# OpenWrt源码目录结构：

* tools和toolchain目录：包含了一些通用命令, 用来生成固件, 编译器, 和C库.
* build dir/host目录：是一个临时目录, 用来储存不依赖于目标平台的工具.
* build dir/toolchain-目录：用来储存依赖于指定平台的编译链. 只是编译文件存放目录无需修改.
* build dir/target-目录：用来储存依赖于指定平台的软件包的编译文件, 其中包括linux内核, u-boot, packages, 只是编译文件存放目录无需修改.
* staging_dir目录：是编译目标的最终安装位置, 其中包括rootfs, package, toolchain.
* package目录：软件包的下载编译规则, 在OpenWrt固件中, 几乎所有东西都是.ipk, 这样就可以很方便的安装和卸载.
* target目录：目标系统指嵌入式设备, 针对不同的平台有不同的特性, 针对这些特性, “target/linux”目录下按照平台进行目录划分, 里面包括了针对标准内核的补丁, 特殊配置等.
* bin目录：编译完OpenWrt的二进制文件生成目录, 其中包括sdk, uImage, u-boot, dts, rootfs构建一个嵌入式系统完整的二进制文件.
* config目录：存放着整个系统的的配置文件.
* docs目录：里面不断包含了整个宿主机的文件源码的介绍, 里面还有Makefile为目标系统生成docs.
* include目录：里面包括了整个系统的编译需要的头文件, 但是是以Make进行连接的.
* feeds目录：扩展软件包索引目录.
* scripts目录：组织编译整个OpenWrt的规则.
* tmp目录：编译文件夹, 一般情况为空.
* dl目录：所有软件的下载目录, 包括u-boot, kernel.
* logs目录：如果编译出错, 可以在这里找到编译出错的log.