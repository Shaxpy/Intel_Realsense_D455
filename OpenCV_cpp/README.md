### Install Opencv
Open a terminal, and follow the steps:
> git clone https://github.com/Shaxpy/Raspberry-Pi4 <br>
> cd Intel_D455/OpenCV_cpp <br>
> sudo chmod +x install.sh <br>
> sudo ./install.sh <br>

#### Building OpenCV for CPP
> sudo -s <br>
> cd /opt <br>
> git clone https://github.com/Itseez/opencv.git <br>
> git clone https://github.com/Itseez/opencv_contrib.git <br>
> cd opencv <br>
> mkdir release <br>
> cd release <br>
> cmake -D BUILD_TIFF=ON -D WITH_CUDA=OFF -D ENABLE_AVX=OFF -D WITH_OPENGL=OFF -D WITH_OPENCL=OFF -D WITH_IPP=OFF -D WITH_TBB=ON -D BUILD_TBB=ON -D WITH_EIGEN=OFF -D WITH_V4L=OFF -D WITH_VTK=OFF -D BUILD_TESTS=OFF -D BUILD_PERF_TESTS=OFF -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=/usr/local -D OPENCV_EXTRA_MODULES_PATH=/opt/opencv_contrib/modules /opt/opencv/ <br>
> make -j4 <br>
> make install <br>
> ldconfig <br>
> exit <br>
> cd Intel_D455/OpenCV_cpp <br>
> sudo cp opencv.pc /usr/local/lib/pkgconfig/opencv.pc <br>
> PKG_CONFIG_PATH=$PKG_CONFIG_PATH:/usr/local/lib/pkgconfig <br>
> export PKG_CONFIG_PATH <br>

- To check if OpenCV is installed
> pkg-config --modversion opencv

