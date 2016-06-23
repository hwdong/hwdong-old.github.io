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

 ![](http://65.media.tumblr.com/4c804b0fda15c6fc2837329754116ee2/tumblr_inline_o97seeEPG41t3innf_500.jpg)  
     3d face registration with 42 pairs of corresponding points


 ![](http://67.media.tumblr.com/5199f7c3fd522149063f96e4e67fd9ea/tumblr_inline_o7yu5vBKub1t3innf_500.jpg)  
    simulate real camera with OpenGL

 ![](https://67.media.tumblr.com/2e21238fd14771d1481b1f610eab9a6d/tumblr_inline_o97txu8nBV1t3innf_540.png) 
    face labeling and segmentation ny my student,chenzhi.  