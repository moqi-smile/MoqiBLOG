****************************
Linux环境配置
****************************

安装代码阅读软件
==============================================

1.1 wine 兼容层
----------------------------------------------

.. note::

        Wine (Wine Is Not an Emulator)[即Wine不是一个模拟器]是一个在Linux和UNIX之上的，Windows 3.x和 Windows APIs的实现。注意，Wine不是Windows模拟器，而是运用API转换技术实做出Linux对应到Windows相对应的函数来调用DLL以运行Windows程序。
        (选自百度百科)

安装 wine

.. code::

    sudo apt-get install wine

在安装的过程中，会跳出一个对话框ttf-mscorefonts-installer”，这个时候只需要按tab键，按ok，然后会再跳出一个对话框，再按yes就没问题了


到这里就安装结束了，安装完以后，会发现～/文件夹下多了一个.wine文件夹，我们以后安装的软件都会放在这个位置

1.2 source insight

.. note::

        Source Insight是一个面向项目开发的程序编辑器和代码浏览器，它拥有内置的对C/C++，C#和Java等程序的分析。能分析源代码并在工作的同时动态维护它自己的符号数据库，并自动显示有用的上下文信息。
        (选自百度百科)

因为source insight是在windows系统下用的软件，linux系统无法直接使用，所以我们需要wine来让我们的linux系统兼容windows软件，在上文我们就介绍了wine怎么安装，接下来我们去下载source insight的软件安装包，这个可以去官网下载。

.. code::

	mkdir -p ~/work/tool
	cd ~/work/tool
    wget https://s3-us-west-2.amazonaws.com/assets.sourceinsight.com/download/v4/release/sourceinsight4095-setup.exe

下载完以后只需要在下载好的的文件夹里输入

.. code::

    wine sourceinsight4095-setup.exe

就能够在Windows安装程序一样，安装source insight，如果你像我一样安装在默认路径下，则source insight在 ~/.wine/drive_c/Program\ Files\ \(x86\)/Source\ Insight\ 4.0/sourceinsight4.exe 下，你以后需要使用到他的时候，你只需要 

.. code::

    wine .wine/drive_c/Program\ Files\ \(x86\)/Source\ Insight\ 4.0/sourceinsight4.exe

就能打开source insight

安装 tftp
====================================================================

