##CTS for ubuntu 16.04
>update:Android N

* 升级系统软件与资源包
 * 
        sudo apt-get upgrade
        sudo apt-get update

* 安装JDK
  * jdk1.8 (Android N)
 
  *     sudo apt-get install openjdk-8-jdk
      
  * jdk-1.7 (Android M)
 
  * 
        sudo add-apt-repository ppa:openjdk-r/ppa
        sudo apt-get update
        sudo apt-get install openjdk-7-jdk

  * > 	
        sudo update-alternatives --config java    //切换jdk版本

* 安装并配置ADB
  * 安装ADB
  * 
        a. sudo apt-get install android-tools-adb
        b. 设备使用USB线连接电脑
        c. echo 0x[0e8d] > ～/.android/adb_usb.ini
  * 设置系统以检测设备
  * 
           以 root权限创建此文件：/etc/udev/rules.d/51-android.rules
           //lsusb 可查看idVendor
        a. SUBSYSTEM=="usb", ATTR{idVendor}=="0e8d", MODE="0666", GROUP="plugdev"
        b. chmod a+r /etc/udev/rules.d/51-android.rules

* [下载最新的android-sdk-linux](https://developer.android.com/studio/index.html)
 *
        下载 build-tools
  
* 配置aapt环境变量
  *
  
        a. 编辑/etc/profile
           底部添加 $ export PATH=$PATH:$HOME/android-sdk-linux/build-tools/<version>
        b. 编辑$.～bashrc
           底部添加 source etc/profile
        c. sudo chomd a+r $HOME/android-sdk-linux/build-tools/<version>/aapt
