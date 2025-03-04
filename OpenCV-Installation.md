# OpenCV Installation

## Overview
This guide will help you set up the dependencies for running a Donkey Car project on a Jetson Nano.

## 1. Install Dependencies

First, update and upgrade your system:

```bash
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install build-essential python3 python3-dev python3-pip libhdf5-serial-dev hdf5-tools nano ntp
```

**Note:** Optionally, you can install RPi.GPIO clone for Jetson Nano if needed for LED or GPIO devices.

## 2. Setup Virtual Environment

To create a virtual environment:
```bash
pip3 install virtualenv
python3 -m virtualenv -p python3 env --system-site-packages
```
To activate the environment
```bash
echo "source env/bin/activate" >> ~/.bashrc
source ~/.bashrc
```

## 3. Install OpenCV

### Swap Space Configuration

The Jetson Nano has only 4GB of RAM, which is insufficient for building OpenCV from source. Follow these steps to create swap space:

```bash
# Allocates 4G of additional swap space at /var/swapfile
sudo fallocate -l 4G /var/swapfile

# Set permissions
sudo chmod 600 /var/swapfile

# Make swap space
sudo mkswap /var/snCVwapfile

# Turn on swap
sudo swapon /var/swapfile

# Automount swap space on reboot
sudo bash -c 'echo "/var/swapfile swap swap defaults 0 0" >> /etc/fstab'

# Reboot
sudo reboot
```

### OpenCV Prerequisites

Install the necessary dependencies for building OpenCV:

```bash
# Update
sudo apt-get update
sudo apt-get upgrade

# Pre-requisites
sudo apt-get install build-essential cmake unzip pkg-config
sudo apt-get install libjpeg-dev libpng-dev libtiff-dev
sudo apt-get install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev
sudo apt-get install libxvidcore-dev libx264-dev
sudo apt-get install libgtk-3-dev
sudo apt-get install libatlas-base-dev gfortran
sudo apt-get install python3-dev
```

# Compiling OpenCV from Source

## Download OpenCV Source Code

```bash
# Create a directory for opencv
mkdir -p AdaptX/cv2
cd AdaptX/cv2

# Download sources
wget -O opencv.zip https://github.com/opencv/opencv/archive/4.1.0.zip
wget -O opencv_contrib.zip https://github.com/opencv/opencv_contrib/archive/4.1.0.zip

# Unzip
unzip opencv.zip
unzip opencv_contrib.zip

# Rename
mv opencv-4.1.0 opencv
mv opencv_contrib-4.1.0 opencv_contrib
```

## Prepare Virtual Environment

```bash
# Install Numpy
pip install numpy==1.16.4
```

## Configure CMake

```bash
# Create a build directory
cd AdaptX/cv2/opencv
mkdir build
cd build

# Setup CMake
cmake -D CMAKE_BUILD_TYPE=RELEASE \
    -D CMAKE_INSTALL_PREFIX=/usr/local \
    -D INSTALL_PYTHON_EXAMPLES=ON \
    -D INSTALL_C_EXAMPLES=OFF \
    -D OPENCV_ENABLE_NONFREE=ON \
    -D OPENCV_EXTRA_MODULES_PATH=~/AdaptX/cv2/opencv_contrib/modules \
    -D PYTHON_EXECUTABLE=~/env/bin/python \
    -D BUILD_EXAMPLES=ON ../opencv
```

## Compile OpenCV

```bash
# Compile (this may take a while)
make -j2
```

**Note:** This compilation process can take considerable time. Feel free to take a break while it runs.

## Install OpenCV

```bash
# Install OpenCV
sudo make install
sudo ldconfig
```

## Link OpenCV to Virtual Environment

```bash
# Go to the folder where OpenCV's native library is built
cd /usr/local/lib/python3.6/site-packages/cv2/python-3.6

# Rename the library
mv cv2.cpython-36m-xxx-linux-gnu.so cv2.so

# Go to your virtual environment's site-packages folder
cd ~/env/lib/python3.6/site-packages/

# Create a symbolic link
ln -s /usr/local/lib/python3.6/site-packages/cv2/python-3.6/cv2.so cv2.so
```

## Verification

Verify the installation:

```bash
# Check the site-packages directory
ls -al
```

## Troubleshooting

- Ensure all paths match your specific installation
- Verify Python version compatibility
- Check that all dependencies are correctly installed
- If encountering issues, double-check CMake configuration

## Additional Resources

- [OpenCV Official Documentation](https://docs.opencv.org/)
- [OpenCV GitHub Repository](https://github.com/opencv/opencv)

**Congratulations!** You have now successfully compiled OpenCV from source for your Jetson Nano.
S

### Alternative OpenCV Installation

If OpenCV is already available in your disc image, you can use this method:

```bash
mkdir ~/mycar
cp /usr/lib/python3.6/dist-packages/cv2.cpython-36m-aarch64-linux-gnu.so ~/mycar/
cd ~/mycar
python -c "import cv2"
```

**Note:** 
- Nvidia has indicated they may drop support for pre-installed OpenCV
- Long-term, building from source is recommended
- The swapfile configuration helps improve performance and prevents memory thrashing

## Troubleshooting
- Ensure you have a stable internet connection
- Check that all dependencies are correctly installed
- Verify Python and pip versions
- If encountering issues, consult the Donkey Car project documentation

## Additional Resources
- [Donkey Car Project Documentation](https://docs.donkeycar.com/)
- [Jetson Nano Developer Resources](https://developer.nvidia.com/embedded/jetson-nano-developer-kit)
