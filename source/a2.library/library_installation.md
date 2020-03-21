[TOC]

# Library Installation Guide

### OpenCV2版本与OpenCV3共存

> 参考:[1. **ubuntu 安装使用多版本opencv](https://blog.csdn.net/heyijia0327/article/details/54575245)
>
> 方案:
>
> Opencv2 apt方式,安装在默认安装路径.
>
> Opencv3 源码安装方式, 安装在/usr/local/opencv3下, 并编译第三方库.
>
> <!--或者可以安装在 /home/junhui/slam_thirdparty/opencv3.4/release/installed-->

* __Step1:安装dependancy__

  ```sh
  #安装编译工具
  sudo apt-get install build-essential
  #安装依赖包
  sudo apt-get install cmake git libgtk2.0-dev pkg-config libavcodec-dev libavformat-dev libswscale-dev
  #安装可选包
  sudo apt-get install python-dev python-numpy libtbb2 libtbb-dev libjpeg-dev libpng-dev libtiff-dev libjasper-dev libdc1394-22-dev
  ```

* __安装OpenCV__

  ```sh
  #2.1源代码 安装opencv3
  cmake 
  -D CMAKE_BUILD_TYPE=Release 
  -D CMAKE_INSTALL_PREFIX=/usr/local/opencv3
  -D OPENCV_EXTRA_MODULES_PATH=/home/junhui/slam_thirdparty/opencv_contrib_XX/modules 
  #第三方库
  ..
  
  make -j4
  sudo make install
  
  #2.2 apt 安装opencv2
  		    sudo apt-get install libopencv-dev(18.04下测得为OpenCV3.2版本
  ```

* __CMakeLists的使用__

  ```sh
  #opencv3
  set(OpenCV_DIR /usr/local/opencv3/share/OpenCV) 
  	    #set(CMAKE_PREFIX_PATH "/usr/local/opencv3")
  				    find_package(OpenCV 3 REQUIRED)
  include_directories(${OpenCV_INCLUDE_DIR})
  target_link_libraries(${OpenCV_LIBS})
  
  #opencv2:
  find_package(OpenCV 2 REQUIRED)
  ```

  

### Cuda 与 cuDNN 安装

> 参考:[Cuda installation -f-Debian Installer ](https://docs.nvidia.com/cuda/cuda-quick-start-guide/index.html#ubuntu-x86_64)
>
> 



### Protobuf:

[wiki_tutorial](https://developers.google.com/protocol-buffers/docs/cpptutorial)