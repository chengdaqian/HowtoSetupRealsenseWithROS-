# HowtoSetupRealsenseWithROS-

## Introduction

HowtoSetupRealsenseWithROS???

That is a great question. In this Repo, I'll show you.

To make Realsense work with ROS, you have to complete two steps:

- Install `librealsense`. It's a library that provides support for Realsense devices. After installing it, you will be able to use the camera with `realsense-view`.
- Install `realsense2_camera`. It's the ROS wrapper for Realsense.

## Instruction

**Install librealsense**

(These steps are copied from https://github.com/IntelRealSense/librealsense/blob/master/doc/distribution_linux.md)

- Add Intel server to the list of repositories :
  `echo 'deb http://realsense-hw-public.s3.amazonaws.com/Debian/apt-repo xenial main' | sudo tee /etc/apt/sources.list.d/realsense-public.list`
  It is recommended to backup /etc/apt/sources.list.d/realsense-public.list file in case of an upgrade.
- Register the server's public key :
  `sudo apt-key adv --keyserver keys.gnupg.net --recv-key 6F3EFCDE`

- Refresh the list of repositories and packages available :
  `sudo apt-get update`

- In order to run demos install:
  `sudo apt-get install librealsense2-dkms`
  `sudo apt-get install librealsense2-utils`
  The above two lines will deploy librealsense2 udev rules, kernel drivers, runtime library and executable demos and tools. Reconnect the Intel RealSense depth camera and run: `realsense-viewer`

- Developers shall install additional packages:
  `sudo apt-get install librealsense2-dev`
  `sudo apt-get install librealsense2-dbg`
  
**Install realsense2_camera**

- Go to `<your_catkin_ws_dir>/src`
- Clone repo: `git clone https://github.com/intel-ros/realsense`
- Go to `<your_catkin_ws_dir>`
- Make and install
  `catkin_make`
  `catkin_make install`
- Try some launch files, see if things work. Launch files' usage instructions can be found at https://github.com/intel-ros/realsense

