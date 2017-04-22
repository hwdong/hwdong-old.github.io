---
layout: post
title: librarys and tools for programming on windows
categories:
- 科技
tags:
- 科技
---

<!--more-->
OpenBlas: you should install "[strawberry perl](http://strawberryperl.com/)" first.

[Intel® Performance Libraries](https://software.intel.com/en-us/performance-libraries) : which include intel MPI, [intel MKL](https://software.intel.com/en-us/intel-mkl/),intel IPP ,nitel TBB, intel DAAL. you can download free version with your university email account.

[Intel Parallel Studio XE](https://software.intel.com/en-us/intel-parallel-studio-xe): a software development suite that helps boost application performance by taking advantage of the ever-increasing processor core count and vector register width available in Intel® Xeon® processors,...

[python 2.7.11](https://www.python.org/ftp/python/2.7.11/python-2.7.11.amd64.msi): numpy, scipy, matplotlib, scikit-image, h5py from Unofficial Windows Binaries for Python Extension Packages webpage and gevent v1.0.2  at ([http://www.lfd.uci.edu/~gohlke/pythonlibs/](http://www.lfd.uci.edu/~gohlke/pythonlibs/)).
```
python -m pip install cython
python -m pip install numpy-1.11.0+mkl-cp27-cp27m-win_amd64.whl
python -m pip install scipy-0.17.0-cp27-none-win_amd64.whl
python -m pip install matplotlib-1.5.1-cp27-none-win_amd64.whl
python -m pip install scikit_image-0.12.3-cp27-cp27m-win_amd64.whl
python -m pip install h5py-2.6.0-cp27-cp27m-win_amd64.whl
```