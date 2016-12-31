 ---
layout: post
title:   windows上安装ubuntu及基础操作
categories:
- IT
tags:
- IT
---

 更新自2014年QQ日志
 

 **
1. U盘安装windows7或windows10**:


（在一台windows机器上）用 [windows 7 dvd usb tool](Windows USB/DVD Download Tool)制作安装windows7或windows10的安装启动u盘，在启动电脑时一直按"Del"键选择U盘启动,然后按照指令安装windows。
 如果要在windows上安装linux（如ubuntu）双系统，则在安装过程分区时，流出足够剩余(free)空间给linux系统。

<!--more-->

 **
2. 在已有windwos系统上安装ubuntu
**
 

  1). 下载ubuntu 并制作USB或DVD安装盘：
       http://howtoubuntu.org/how-to-install-ubuntu-14-04-trusty-tahr   
      usb制作工具制作usb安装盘   
    
  
  
  2). window系统上留出一块多余空间如50G （具体过程：桌面上选中计算机 -> 右键菜单选择管理 -> 选择磁盘管理，右键菜单选择压缩卷. 压缩卷的功能是将分区中的部分空间去除,成为空闲的空间） 
   
  

 3)  windows系统启动时，按del键盘进入BIOS，选择首选启动项为 U盘而不是硬盘。  
   注意:  安装画面选择安装模式时要选 "其他(other)", 防止覆盖windows系统
  


  4） usb启动后进入ubuntu安装过程，此时需要进行4个分区(网上教程有误，需要都作为 逻辑分区),即按照下面的a),b),c)进行分区,即主要哈ufenweisange分区： / 、/home 、swap 。
      

   假如有200G的空间，那么其中swap分区放在最后，大概2G差不多了。而/我想弄一个60G和90G之间应该可以了。其余的都留给/home分区！

   a)   至少25,000M             logical                   ext4                 root分区，    其 Mounting Point: /      
        
  b)  除去/和swap的其余空间， 留给/home分区                ext4                  home分区      Mounting Point: / home
         

   c)  2048M           logical ( 即逻辑分分区)            swap分区      
         

   d） 200M             logical ( 即逻辑分分区)            ext4                  boot                    Mounting Point: / boot             这一步不需要！

  

**3. 系统环境
** 
 

**4. 其他**

       挂载u盘，往u盘上拷贝数据： mount -o remount,rw /*** U盘的挂载点
