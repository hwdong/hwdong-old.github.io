---
layout: post
title: Implemantation of “Color Map Optimization for 3D Reconstruction with Consumer Depth Cameras”
categories:
- 科技
tags:
- 科技
---
 
This morning I spend a few hours (while I am watching TV program)to implement the algorithm in the paper "[Color Map Optimization for 3D Reconstruction with Consumer Depth Cameras](http://vladlen.info/publications/color-map-optimization-for-3d-reconstruction-with-consumer-depth-cameras/)" . 
<!--more-->

It is very simple to implememt. The author din't provide the raw data for test, I will test it a few days later when we captured some high quality test data.  The result of the paper looks like this:

![](http://vladlen.info/wp-content/uploads/2014/04/color-mapping.jpg)

This is a test for my implementation. 
![](http://blog.hwdong.com/images/color_map.jpg)

![](http://blog.hwdong.com/images/color_map_2.jpg)

From the botton picure, we can see the color map has been optimized resulting better fitting of feature points. Although the result is not good as the paper. I think it may be due to the poor quality captured images (the resolution of image is low (640*480) ,the paper used high resolution (1280*1024) images.  Some of them we captured are blured,we should removed these images) and the eye sometimes open and sometimes closed (always moving not a static object).
  
You can download my program from [here](http://hwdong.com/programs/ColorMap_Optimization_zip.zip). But you must email me so that I can tell you how to run this program. If someone need this in your code,you can ask me to send you an API library.

