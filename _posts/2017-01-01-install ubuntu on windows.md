---
layout: post
title:   windows上安装ubuntu及基础操作
categories:
- IT
tags:
- IT
---

更新自2014年QQ日志 

**1. U盘安装windows7或windows10**:

(在一台windows机器上)用 [windows 7 dvd usb tool](Windows USB/DVD Download Tool)制作安装windows7或windows10的安装启动u盘，在启动电脑时一直按"Del"键选择U盘启动,然后按照指令安装windows。如果要在windows上安装linux（如ubuntu）双系统，则在安装过程分区时，留出足够剩余(free)空间给linux系统。

<!--more-->

**2. 在已有windwos系统上安装ubuntu** 

1). [下载ubuntu 并制作USB或DVD安装盘](http://howtoubuntu.org/how-to-install-ubuntu-14-04-trusty-tahr);

[usb制作工具制作usb安装盘](https://help.ubuntu.com/community/Installation/FromUSBStickQuick)  
   
![](http://s5.51cto.com/wyfs02/M00/27/6B/wKioL1Ny1O2gFAIHAACh9GlDXUo023.jpg) 

    
2). window系统上留出一块多余空间如50G （具体过程：桌面上选中计算机 -> 右键菜单选择管理 -> 选择磁盘管理，右键菜单选择压缩卷. 压缩卷的功能是将分区中的部分空间去除,成为空闲的空间） 
   
3)  windows系统启动时，按del键盘进入BIOS，选择首选启动项为 U盘而不是硬盘。  
   
 **注意:**  安装画面选择安装模式时要选 那个’Something else’ 选项, 防止覆盖windows系统


![](https://assets.ubuntu.com/v1/b42312cd-download-desktop-install-ubuntu-desktop_4.jpg)
  
4） usb启动后进入ubuntu安装过程，此时需要进行4个分区(网上教程有误，都应选逻辑分区),即按照下面的a),b),c)分为3个分区： / 、/home 、swap 。
      

假如有200G的空间，那么其中swap分区放在最后，大概2G差不多了。而/我想弄一个60G和90G之间应该可以了。其余的都留给/home分区！

```
a)   至少25,000M             logical                   ext4                 root分区，    其 Mounting Point: /      
        
b)  除去/和swap的其余空间， 留给/home分区                ext4                  home分区      Mounting Point: / home
         
c)  2048M           logical ( 即逻辑分分区)            swap分区      
         
d） 200M             logical ( 即逻辑分分区)            ext4                  boot                    Mounting Point: / boot             这一步不需要！
```

 我的电脑安装了windows10和ubuntu14.04,ubuntu16.04这3个系统。

**3. 系统配置** 

 1).网络的配置，网上转载的基于命令行的网络配置程序的文章既复杂又过时了，其实只要通过GUI界面很容易配置。注意使用ifconfig查看网卡驱动是否正确安装了！

 网速慢： 网上东抄西抄的文章都是胡说，因为ubuntu已经自带了dnsmasq，我都试验过，没效果的！ 最简单的方法是在网络设置里设置一下OpenDNS域名服务器就行了！

 2) 汉字输入:参考[http://blog.csdn.net/up_seeker/article/details/40859777](http://blog.csdn.net/up_seeker/article/details/40859777)

 google输入法:

    a)CTRL+ALT+T“组合键打开terminal窗口，输入下面的命令：

      sudo apt-get install ibus-googlepinyin

    b)重启或注销     

    c)运行 sudo ibus-setup , 在custom input method中添加(add)google输入法。

    d)系统设置(system setting) -> Personal->Text Entry里添加刚才的google输入法和English(US) 这2个输入法。
    重启系统。就可以用super+space键进行中英文切换了！
 
  
**4. 编程环境**

1)  安装基本编程工具

```
    sudo apt-get update    
    sudo apt-get install git
    sudo apt-get install build-essential
    sudo apt-get install cmake
    sudo apt-get install libx11-dev
    sudo apt-get install mesa-common-dev libgl1-mesa-dev libglu1-mesa-dev
    sudo apt-get install libxrandr-dev
    sudo apt-get install libxi-dev
    sudo apt-get install libxmu-dev
    sudo apt-get install libblas-dev

    sudo apt-get install cmake
    sudo apt-get install cmake-qt-gui

    sudo apt-get install libboost-dev 

    sudo apt-get install alien  # 以便安装rpm包 sudo alien -i mxxx.rpm
```

安装多个编译器gcc/g++:

```
    #查询
    which g++ gcc  
    ls /usr/bin/gcc* 
    sudo update-alternatives --config gcc   
    #安装
    sudo add-apt-repository ppa:ubuntu-toolchain-r/test
    sudo apt-get update
    sudo apt-get install gcc-5 g++-5 gcc-4.9 g++-4.9
    sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-5 60 --slave /usr/bin/g++ g++ /usr/bin/g++-5
sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-4.9 40 --slave /usr/bin/g++ g++ /usr/bin/g++-4.9
    sudo update-alternatives --config gcc
```

[getting-installing-gcc-g-4-9-on-ubuntu](http://askubuntu.com/questions/428198/getting-installing-gcc-g-4-9-on-ubuntu)

) 

install CUDA8 on ubuntu(安装CUDA8) ：
不要安装driver，只要[下载](https://developer.nvidia.com/cuda-downloads)一个CUDA8安装就可以了
    
方法一：

ALT+ALt+F1 进入(enter) terminal;

```python
      sudo  /etc/init.d/lightdm stop 或者sudo  /etc/init.d/gdm stop ; 
      sudo chmod +x cuda*.run;
      sudo ./cuda*.run; 
      sudo  /etc/init.d/lightdm  restart  
```

输入$ sudo gedit /etc/profile，打开 gedit ，最后两行输入

```python
export PATH=/usr/local/cuda-8.0/bin:$PATH
export LD_LIBRARY_PATH=/usr/local/cuda-8.0/lib64:$LD_LIBRARY_PATH

```

方法二(似乎不行)：
参考：[http://www.th7.cn/system/lin/201607/173609.shtml](http://www.th7.cn/system/lin/201607/173609.shtml)

3) 常用库及IDE环境

 [install opencv](http://milq.github.io/install-opencv-ubuntu-debian/) :
 ```sudo apt-get install libopencv-dev python-opencv```
  
  安装Eclipse:
```  
  sudo apt-get install eclipse eclipse-cdt g++
```  

4). 软件包的安装与管理：（http://zhouliang.pro/2011/10/23/ubuntu-apt-aptitude-dpkg/ ），如 

  dpkg -l |grep forefox 

  查看firefox程序的安装信息，

 rpm包在ubuntu下不支持，需要转换成debian,参考[该文章](http://superuser.com/questions/607493/rpm-should-not-be-used-directly-install-rpm-packages).

**5. 其他**

开机启动某应用程序：点击Windows按键，输入Startup，可打开启动应用程序，在其中可以添加开机启动项。

Chrome里打开下载续传功能：chrome://flags

众所周知原因gti clone很慢，会出错，如'error: RPC failed:...', 可输入如下命令：git config --global http.postBuffer 524288000 
