### Experiments with Intel Realsense D455 Depth Camera
- [Beginning with Raspberry Pi4](https://github.com/Shaxpy/Raspberry-Pi4)
- [Installing Librealsense SDK 2.0](https://github.com/IntelRealSense/librealsense/blob/master/doc/installation.md)
- [Setup OpenCV for C/C++ on Pi](https://github.com/Shaxpy/Intel_Realsense_D455/tree/master/OpenCV_cpp)
- [Take a pic on D455!](https://github.com/Shaxpy/Intel_Realsense_D455/tree/master/Testing/intel)
#### Calibrating normal USB Cameras
- Edit usb_cam_node.cpp, and change the pixel_format to "yuyv"
- Run the following in different terminals-
> roscore <br>
> rosrun camera_calibration cameracalibrator.py --size 8x6 --square 0.108 image:=/usb_cam/image_raw camera:=/dev/video0 --no-service-check --approximate=0.1 <br>
> rosrun usb_cam usb_cam_node <br>
Refer http://wiki.ros.org/camera_calibration/Tutorials/MonocularCalibration#Running_the_Calibration_Node

