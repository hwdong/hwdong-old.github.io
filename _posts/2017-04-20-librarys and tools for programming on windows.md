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

[Python 2.7.11 64bit](https://www.python.org/ftp/python/2.7.11/python-2.7.11.amd64.msi): numpy, scipy, matplotlib, scikit-image, h5py from Unofficial Windows Binaries for Python Extension Packages webpage   at ([http://www.lfd.uci.edu/~gohlke/pythonlibs/](http://www.lfd.uci.edu/~gohlke/pythonlibs/)).
```
python -m pip install cython
python -m pip install numpy-1.12.1+mkl-cp27-cp27m-win_amd64.whl
python -m pip install scipy-0.19.0-cp27-none-win_amd64.whl
python -m pip install matplotlib-2.0.0-cp27-none-win_amd64.whl
python -m pip install scikit_image-0.13.0-cp27-cp27m-win_amd64.whl
python -m pip install h5py-2.7.0-cp27-cp27m-win_amd64.whl
python -m pip list
```
When you install VS2015(VS2013...),you should choose to include python. If not,you can install Microsoft Visual C++ Compiler for Python 2.7, downloaded at (https://www.microsoft.com/en-us/download/details.aspx?id=44266) and install it by :
```
 msiexec /i VCForPython27.msi ALLUSERS=1
```

[CUDA8](https://developer.nvidia.com/cuda-downloads) and [cuDNN](https://developer.nvidia.com/cudnn)

[Graphviz](www.graphviz.org/Download.php). Note: The installation directory can not contain space.

After all finished, Download [gevent-1.2.1-cp27-none-win_amd64.whl](http://www.lfd.uci.edu/~gohlke/pythonlibs/) and install it.

```
python -m pip install gevent-1.2.1-cp27-none-win_amd64.whl
```