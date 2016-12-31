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

(在一台windows机器上)用 [windows 7 dvd usb tool](Windows USB/DVD Download Tool)制作安装windows7或windows10的安装启动u盘，在启动电脑时一直按"Del"键选择U盘启动,然后按照指令安装windows。如果要在windows上安装linux（如ubuntu）双系统，则在安装过程分区时，流出足够剩余(free)空间给linux系统。

<!--more-->

(在一台windows机器上)用 [windows 7 dvd usb tool](Windows USB/DVD Download Tool)制作安装windows7或windows10的安装启动u盘，在启动电脑时一直按"Del"键选择U盘启动,然后按照指令安装windows。
 如果要在windows上安装linux（如ubuntu）双系统，则在安装过程分区时，流出足够剩余(free)空间给linux系统。

**2. 在已有windwos系统上安装ubuntu** 

1). [下载ubuntu 并制作USB或DVD安装盘](http://howtoubuntu.org/how-to-install-ubuntu-14-04-trusty-tahr);

[usb制作工具制作usb安装盘](https://help.ubuntu.com/community/Installation/FromUSBStickQuick)  
   
![](http://s5.51cto.com/wyfs02/M00/27/6B/wKioL1Ny1O2gFAIHAACh9GlDXUo023.jpg) 

    
2). window系统上留出一块多余空间如50G （具体过程：桌面上选中计算机 -> 右键菜单选择管理 -> 选择磁盘管理，右键菜单选择压缩卷. 压缩卷的功能是将分区中的部分空间去除,成为空闲的空间） 
   
3)  windows系统启动时，按del键盘进入BIOS，选择首选启动项为 U盘而不是硬盘。  
   注意:  安装画面选择安装模式时要选 "其他(other)", 防止覆盖windows系统

**注意：**  选择最下面的那个’Something else’ 选项

![](https://assets.ubuntu.com/v1/b42312cd-download-desktop-install-ubuntu-desktop_4.jpg)
  
4） usb启动后进入ubuntu安装过程，此时需要进行4个分区(网上教程有误，需要都作为 逻辑分区),即按照下面的a),b),c)进行分区,即主要哈ufenweisange分区： / 、/home 、swap 。
      

假如有200G的空间，那么其中swap分区放在最后，大概2G差不多了。而/我想弄一个60G和90G之间应该可以了。其余的都留给/home分区！

a)   至少25,000M             logical                   ext4                 root分区，    其 Mounting Point: /      
        
b)  除去/和swap的其余空间， 留给/home分区                ext4                  home分区      Mounting Point: / home
         
c)  2048M           logical ( 即逻辑分分区)            swap分区      
         
d） 200M             logical ( 即逻辑分分区)            ext4                  boot                    Mounting Point: / boot             这一步不需要！

**3. 系统配置** 

 1).网络的配置，网上转载的基于命令行的网络配置程序的文章既复杂又过时了，其实只要通过GUI界面很容易配置。注意使用ifconfig查看网卡驱动是否正确安装了！

 网速慢： 网上东抄西抄的文章都是胡说，因为ubuntu已经自带了dnsmasq，我都试验过，没效果的！ 最简单的方法是在网络设置里设置一下OpenDNS域名服务器就行了！另外，浏览器需要安装好flash player插件，一旦安装好该插件后，你会发现网速马上变快了，浏览网页比Windows7 环境下要快！

 2) 汉字输入:参考[](http://blog.csdn.net/up_seeker/article/details/40859777)

 google输入法:

    a)CTRL+ALT+T“组合键打开terminal窗口，输入下面的命令：

      sudo apt-get install ibus-googlepinyin

    b)系统设置(system setting) -> Personal->Text Entry里添加刚才的google 输入法就可以。

    c)重启系统。就可以用super+space键进行中英文切换了！
 
 3. 软件包的安装与管理：（http://zhouliang.pro/2011/10/23/ubuntu-apt-aptitude-dpkg/ ），如 

  dpkg -l |grep forefox 

  查看firefox程序的安装信息，

 rpm包在ubuntu下部支持，需要转换成debian: http://superuser.com/questions/607493/rpm-should-not-be-used-directly-install-rpm-packages。

**编程环境**

1) ubuntu16以下版本如果要用g++4.9，则可以安装（install） g++4.9 : 
[getting-installing-gcc-g-4-9-on-ubuntu](http://askubuntu.com/questions/428198/getting-installing-gcc-g-4-9-on-ubuntu)

2)  CUDA8 安装：
    不要安装driver，只要[下载](https://developer.nvidia.com/cuda-downloads)一个CUDA8就可以了
    方法一：

ALT+ALt+F1 进入terminal;

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

方法二：
参考：[http://www.th7.cn/system/lin/201607/173609.shtml](http://www.th7.cn/system/lin/201607/173609.shtml)


**5. 其他**

[挂载u盘](http://jingyan.baidu.com/article/f0062228dc2aa6fbd3f0c8ec.html)，往u盘上拷贝数据： mount -o remount,rw /*** U盘的挂载点

开机启动某应用程序：点击Windows按键，输入Startup，可打开启动应用程序，在其中可以添加开机启动项。

Chrome里打开下载续传功能：chrome://flags
