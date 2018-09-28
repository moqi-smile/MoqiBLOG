openwrt
*************************************************************************

1. 环境搭建
=========================================================================

1.1 安装依赖
-------------------------------------------------------------------------

.. code::

	sudo apt-get install subversion build-essential libncurses5-dev zlib1g-dev gawk git ccache gettext libssl-dev xsltproc


1.2 获取源码
-------------------------------------------------------------------------

.. code::

	mkdir -p ~/work/sources/
	cd ~/work/sources/
	https://github.com/openwrt/openwrt.git

1.3 编译源码
-------------------------------------------------------------------------

更新安装包

.. code::
	
	cd ~/work/sources/openwrt/
	./scripts/feeds update -a
	./scripts/feeds install -a

选择开发平台, 我用的是联发科的7628

.. code::

	make menuconfig

输入上面的指令以后就会弹出一个菜单, 选择

.. code::

	Target System --->
		MediaTek Ralink MIPS
	
	Subtarget --->
		MT76x8 based boards

这样我们就选好了7628作为我们的开发平台, 接下来勾选以下选项, 这个是为了生成交叉编译链

.. code::

	Package the OpenWrt-based Toolchain

这样我们就将所有准做好了, 接下来编译源码

.. code::

	make V=s

编译源码的时间十分漫长, 大概需要四五个小时, 中间还需要下载一些软件包, 如果希望能快些编译好的话可以先下载这些软件包, 我已经将这些软件包上传到我的github上了, 地址是

.. code::

	https://github.com/moqi-smile/openwrt-dl.git

编译完以后, 可以在以下路径看到固件, 固件名字是 openwrt-ramips-mt76x8-mt7628-squashfs-sysupgrade.bin

.. code::

	~/work/sources/openwrt/bin/targets/ramips/mt76x8

