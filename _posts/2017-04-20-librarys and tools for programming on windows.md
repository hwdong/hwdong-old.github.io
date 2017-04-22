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

[Intel® Performance Libraries](https://software.intel.com/en-us/performance-libraries) : which include intel MPI, [intel MKL](https://software.intel.com/en-us/intel-mkl/),intel IPP ,nitel TBB, intel DAAL. you can download free version with your university email account. You can set environment variables for these tools.For example, set **MKL_ROOT** to "C:\Program Files (x86)\IntelSWTools\compilers_and_libraries_2017.2.187\windows\mkl"


[Intel Parallel Studio XE](https://software.intel.com/en-us/intel-parallel-studio-xe): a software development suite that helps boost application performance by taking advantage of the ever-increasing processor core count and vector register width available in Intel® Xeon® processors,...


[boost](http://www.boost.org/users/download/) 

[https://github.com/google/protobuf](https://github.com/google/protobuf),you can download binary[protoc-3.0.0-win32.zip](https://github.com/google/protobuf/releases/tag/v3.0.0)

[ninja](https://github.com/ninja-build/ninja/releases)

[Python 2.7.11 64bit](https://www.python.org/ftp/python/2.7.11/python-2.7.11.amd64.msi): numpy, scipy, matplotlib, scikit-image, h5py from Unofficial Windows Binaries for Python Extension Packages webpage   at ([http://www.lfd.uci.edu/~gohlke/pythonlibs/](http://www.lfd.uci.edu/~gohlke/pythonlibs/)).
```
python -m pip install cython
python -m pip install numpy-1.12.1+mkl-cp27-cp27m-win_amd64.whl
python -m pip install scipy-0.19.0-cp27-cp27m-win_amd64.whl
python -m pip install matplotlib-2.0.0-cp27-cp27m-win_amd64.whl
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

If Pillow is not installed ,you can install [Pillow-3.1.1.win-amd64-py2.7.exe](https://pypi.python.org/pypi/Pillow/3.1.1)

After all finished, Download [gevent-1.2.1-cp27-none-win_amd64.whl](http://www.lfd.uci.edu/~gohlke/pythonlibs/) and install it.

```
python -m pip install gevent-1.2.1-cp27-none-win_amd64.whl
```