---
layout: post
title: Rotation Matrix between first and second camera coordinate systems
categories:
- 科技
tags:
- 科技
---

<!--more-->
 I think the opencv document is not clear when explain the "stereoCalibrate". It just say R is "Rotation Matrix between first and second camera coordinate systems". But from the first camera to second camera or  vice versa ? 

    Mat CM1 = Mat(3, 3, CV_64FC1);

    Mat CM2 = Mat(3, 3, CV_64FC1);

    Mat D1, D2;

    Mat R, T, E, F;


    stereoCalibrate(objectPoints, imagePoints1, imagePoints2, 
                    CM1, D1, CM2, D2, img1.size(), R, T, E, F,
                    cvTermCriteria(CV_TERMCRIT_ITER+CV_TERMCRIT_EPS, 100, 1e-5), 
                    CV_CALIB_SAME_FOCAL_LENGTH | CV_CALIB_ZERO_TANGENT_DIST);

CM1 - Camera Matrix of first camera.

CM2 - Camera Matrix of second camera.

D1 - Distortion coeff matrix of first camera.

D2 - Distortion coeff matrix of second camera.

R - Rotation Matrix between first and second camera coordinate systems.

T - Translation vector between the coordinate systems of the cameras.

E - Essential matrix.

F - Fundamental matrix.

The ducoment of OpenCV should just give a equation such as :

    P2 = R *P1 + T 
    
The meaning will be very clear!     
