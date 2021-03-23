### Setup Intel Realsense D455 Depth Camera
- [Beginning with Raspberry Pi4](https://github.com/Shaxpy/Raspberry-Pi4)
- Install ROS-[ROS Melodic](http://wiki.ros.org/melodic/Installation/Ubuntu)
- ROS wrapper for Realsense D400 series - [realsense-ros](https://github.com/IntelRealSense/realsense-ros)
#### Installing Intel® RealSense™ SDK2.0
> $ sudo apt-get install libusb-1.0-0-dev <br>
$ git clone https://github.com/IntelRealSense/librealsense.git <br>
$ cd librealsense/ <br>
$ mkdir build && cd build <br>
$ cmake ../ -DFORCE_RSUSB_BACKEND=true -DBUILD_PYTHON_BINDINGS=true -DCMAKE_BUILD_TYPE=release -DBUILD_EXAMPLES=true -DBUILD_GRAPHICAL_EXAMPLES=true <br>
$ sudo make uninstall && make clean && make && sudo make install <br>
- Debian install for Realsense SDK2.0 -[librealsense/distribution](https://github.com/IntelRealSense/librealsense/blob/master/doc/distribution_linux.md#installing-the-packages)
- Some patches for Ubuntu -[librealsense/installation](https://github.com/IntelRealSense/librealsense/blob/master/doc/installation.md) <br>
#### Working with D455
- [Setup OpenCV for C/C++ ](https://github.com/Shaxpy/Intel_Realsense_D455/tree/master/OpenCV_cpp)
- [Take a pic on D455!](https://github.com/Shaxpy/Intel_Realsense_D455/tree/master/Testing/intel)
##### Calibrating normal USB Cameras
- Edit usb_cam_node.cpp, and change the pixel_format to "yuyv"
- Run the following in different terminals-
> roscore <br>
> rosrun camera_calibration cameracalibrator.py --size 8x6 --square 0.108 image:=/usb_cam/image_raw camera:=/dev/video0 --no-service-check --approximate=0.1 <br>
> rosrun usb_cam usb_cam_node <br>
Refer http://wiki.ros.org/camera_calibration/Tutorials/MonocularCalibration#Running_the_Calibration_Node

