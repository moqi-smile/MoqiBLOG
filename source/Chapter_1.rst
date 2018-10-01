****************************
Linux环境配置
****************************

====================================================================
安装代码阅读软件
====================================================================


====================================================================
安装 tftp
====================================================================

以下操作全都是在用户权限下操作的

安装软件

.. code::
		
	sudo apt-get install tftp-hpa tftpd-hpa

创建目录

.. code::

	mkdir ~/work/tftpshare

创建配置文件 **/etc/default/tftpd-hpa**

.. code::

	sudo vi /etc/default/tftpd-hpa

在文件内输入

.. code::

	TFTP_USERNAME="tftp"
	TFTP_DIRECTORY="/home/moqi/work/tftpshare" # 这里是你的tftpd-hpa的服务目录,这个想建立在哪里都行但要用绝对路径,不要用相对路径
	TFTP_ADDRESS="0.0.0.0:69"
	TFTP_OPTIONS="-l -c -s"

重启服务

.. code::

	sudo service tftpd-hpa restart

测试，先创建一个文件并输入一些字符

.. code::

	cd ~/work
	echo abcd >> ~/work/tftpshare/text

进入tftp服务, 并获取text文件

.. code::

	tftp localhost
	tftp> get text
	tftp> q

查看下载了的 **text** 文件, 如果有我们刚刚输入的 **abcd** 则证明搭建成功

