***************
openwrt
***************

环境搭建
=========================================================================

	我用的环境是 ubuntu16.04

1.1 安装依赖软件
-------------------------------------------------------------------------

.. code:: bash

    sudo apt-get install subversion build-essential libncurses5-dev zlib1g-dev gawk git ccache gettext libssl-dev xsltproc


1.2 获取源码
-------------------------------------------------------------------------

.. code:: bash

	git clone https://github.com/openwrt/chaos_calmer.git


1.2 编译前的准备
-------------------------------------------------------------------------

备份配置文件

.. code:: bash

	cd openwrt
	cp feeds.conf.default feeds.conf

添加LinkIt Smart 7688 Feed：
	我用的Mt7688, 但是原生的openwrt编译出来的固件没有7688的wifi驱动, 所以我要添加联发科的驱动, 如果你用的不是7688. 这一步可跳过

.. code:: bash

	echo src-git linkit https://github.com/MediaTek-Labs/linkit-smart-7688-feed.git >> feeds.conf

更新并安装用于构建固件的所有可用包

.. code:: bash

	./scripts/feeds update
	./scripts/feeds install -a


选择我们要使用的芯片

.. figure:: _static/Selection_chip.png
    :align: center
    :figclass: align-center

设计第一个程序 Hello world
=========================================================================

1.1
