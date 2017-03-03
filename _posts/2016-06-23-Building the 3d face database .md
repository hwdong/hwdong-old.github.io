---
layout: post
title: Building the 3d face database 
categories:
- 科技
tags:
- 科技
---

 In these two months, I am busing with writing programs to build 3d face database for my graduate students. I wrote kienct calibration programs for kinect one and kinect 2 and modified the offical exampls to save data we may need in the future such as color images ,depth images,camera poses.
 <!--more-->
  Then I wrote little programs  to check the data such as camera poses returned by kinect sdk and discovered the format of camera pose returned by kienct sdk is very strange. There are some little program to align the two face using coordinate systems computed from sysmetric pairs of points in a model. Now We can register two face models with a few corresponing points such as 42 pairs of points. Mode info can be visited from my tumblr blog (It is blocked by GFW).

 ![](http://blog.hwdong.com/images/face_reg.png)  
     3d face registration with 42 pairs of corresponding points


 ![](http://blog.hwdong.com/images/sim_camera.png) 
    simulate real camera with OpenGL

 
 