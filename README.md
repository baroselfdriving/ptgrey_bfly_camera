
### Overview
This repository holds code of a [ROS](http://www.ros.org) package for image acquisition with [Black Fly](https://www.ptgrey.com/blackfly-gige-poe-cameras) camera. It is basically a ROS wrapper of the low-level API provided by [Ponit Grey](https://www.ptgrey.com/), the manufacturer of the camera. The ROS node can be configured to act as a server or as publisher at a given rate. 

![Black Fly Camera](media/bfly_camera.jpg)

### Dependencies
The package has been tested with the following dependencies:
* Ubuntu 16.04
* CMake + gcc
* [ROS Kinetic](http://wiki.ros.org/kinetic)
* [OpenCV v3.1](http://www.opencv.org/) (shipped with ROS Kinetic)
* FlyCapture2 (propietary SDK from the manufacturer)


To install the FlyCapture2 SDK dependency:

1. Download the SDK from the [Point Grey's wbsite](https://www.ptgrey.com/support/downloads)
2. Install it with
```shell 
$ sudo To do ...
```


### Download and Build This ROS package
Download to your ROS workspace /src, with the command:
```shell
$ git clone https://github.com/beta-robots/ptgrey_bfly_camera.git
```
and from your ROS workspace, build it with:
```shell
$ catkin_make --only-pkg-with-deps ptgrey_bfly_camera
```

### Camera Operation
Execute the flycap tool to configure the IP of your camera
```shell
$ flycap
```
Run the node (by default a rviz window will appear)
```shell
$ roslaunch ptgrey_bfly_camera ptgrey_bfly_camera.launch 
```
If you are operating the node in run mode "SERVER", from another terminal request the image capture service with the number of images requested. 
```shell
$ rosservice call /ptgrey_bfly_camera/bfly_server "num_images: 10"
```

### Troubleshooting
The tool flycap has a set of options to configure the camera
```shell
$ flycap
```


