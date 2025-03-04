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
# For actual installation of OpenCV refer the following link:

[Open-CV Installation](https://pyimagesearch.com/2018/08/15/how-to-install-opencv-4-on-ubuntu/)

## Below are some points for reference while installation of OpenCV:

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
