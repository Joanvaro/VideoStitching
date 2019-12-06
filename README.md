# VideoStitching
Implementation of stitching algorithm applied in video, It is tested on a Raspberry Pi3 B+ on Rapsbian version September 2019. The Stitching algorithm is implemented in python using OpenCV

## Installation
In Order to run the program the following package must be installed:
- Python3
- OpenCV
- NumPy
- Imutils

For the installation of OpenCV the following instructions are needed:
``` bash
$ sudo apt-get update && sudo apt-get upgrade
$ sudo apt-get install build-essential cmake pkg-config
$ sudo apt-get install libjpeg-dev libtiff5-dev libjasper-dev libpng12-dev
$ sudo apt-get install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev
$ sudo apt-get install libxvidcore-dev libx264-dev
$ sudo apt-get install libgtk2.0-dev libgtk-3-dev
$ sudo apt-get install libcanberra-gtk*
$ sudo apt-get install libatlas-base-dev gfortran
$ sudo apt-get install python2.7-dev python3-dev
```
The version of OpenCV used for testing is 3.4.7, use the following commands to get it:
``` bash
$ wget -O opencv.zip https://github.com/opencv/opencv/archive/3.4.7.zip
$ unzip opencv.zip
$ wget -O opencv_contrib.zip https://github.com/opencv/opencv_contrib/archive/3.4.7.zip
$ unzip opencv_contrib.zip
```
OpenCV requieres the python library NumPy, to install it copy the following command:
``` bash
 pip3 install numpy
``
For building OpenCV:
``` bash
$ cd ~/opencv-3.4.7/
$ mkdir build
$ cd build
$ cmake -D CMAKE_BUILD_TYPE=RELEASE \
    -D CMAKE_INSTALL_PREFIX=/usr/local \
    -D OPENCV_EXTRA_MODULES_PATH=~/opencv_contrib-3.4.7/modules \
    -D ENABLE_NEON=ON \
    -D ENABLE_VFPV3=ON \
    -D BUILD_TESTS=OFF \
    -D INSTALL_PYTHON_EXAMPLES=OFF \
    -D OPENCV_ENABLE_NONFREE=ON \
    -D CMAKE_SHARED_LINKER_FLAGS='-latomic' \
    -D BUILD_EXAMPLES=OFF ..
$ make -j4
$ sudo make install
$ sudo ldconfig
```

## Usage
``` bash
python3 video_stitch.py
```
## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## Authors
- Cuevas Munguia Jorge Luis
- Paredes Magaña Miguel Angel
- Valdez Rodriguez Jose Antonio
