# AdaptX

## Description :

AdaptX is a modular autonomous system designed for seamless integration with various robotic platforms. Currently, it is being developed using an RC car as a test platform, enabling autonomous navigation, mapping, and object detection. Powered by Jetson Nano, X2 RPLiDAR, and Raspberry Pi V2 Camera, AdaptX leverages cutting-edge AI and SLAM technologies to achieve real-time perception and decision-making.

With a web-based interface built using Flask, users can remotely start and manage key processes such as LiDAR-based mapping and camera-based object detection. The system provides live streaming of object detection and Hector SLAM mapping, making it a versatile solution for robotics and automation applications.

Key Features :<br> 
✅ Autonomous Navigation – SLAM-based path planning and obstacle avoidance.<br>
✅ Mapping – Real-time mapping using Hector SLAM.<br>
✅ Object Detection – YOLO-powered object recognition.<br>
✅ Web Control Interface – Start/stop processes via a Flask-based dashboard.<br>
✅ Live Streaming – View object detection and SLAM mapping on the web.


## Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [Hardware Requirements](#hardware-requirements)
- [Software Requirements](#software-requirements)
- [Installation & Setup](#installation--setup)
- [System Architecture](#system-architecture)
- [Usage](#usage)
  - [Starting the Web Interface](#starting-the-web-interface)
  - [Enabling LiDAR & Mapping](#enabling-lidar--mapping)
  - [Running Object Detection](#running-object-detection)
  - [Live Feed & Web Control](#live-feed--web-control)
- [Configuration](#configuration)
- [Credits & References](#credits--references)


## Introduction

**AdaptX** is a modular autonomous system designed for seamless integration with various robotic platforms. Currently, it is being developed using a **4-wheel RC car** as a test platform to enable **autonomous navigation, real-time mapping, and object detection**.

Built on the **Jetson Nano** and powered by **X2 RPLiDAR, Raspberry Pi V2 Camera, and Arduino**, AdaptX leverages cutting-edge **AI and SLAM** technologies to achieve real-time perception and intelligent decision-making. The system provides a **web-based interface** using Flask, allowing users to remotely start and manage core processes such as **LiDAR-based mapping** and **camera-based object detection**. The live feed of both **object detection** and **Hector SLAM mapping** is accessible through the web interface, making AdaptX a versatile solution for robotics and automation applications.

This project serves as an **adaptable plug-and-play module** that can be integrated with different robotic platforms in the future, beyond the initial RC car testbed.

## Features

✅ **Autonomous Navigation** – Uses **SLAM (Simultaneous Localization and Mapping)** for real-time path planning and obstacle avoidance.  

✅ **Real-time Mapping** – Implements **Hector SLAM** with **X2 RPLiDAR** for efficient environment mapping.  

✅ **Object Detection** – Utilizes **YOLO (You Only Look Once)** for real-time object recognition and tracking.  

✅ **Web-based Control** – A **Flask-powered dashboard** allows users to start/stop key processes like LiDAR and camera remotely.  

✅ **Live Data Streaming** – Provides **real-time visualization** of object detection and SLAM mapping through the web interface.  

✅ **Adaptable & Scalable** – Designed as a **modular system**, AdaptX can be integrated with different robotic platforms beyond the initial RC car setup.  

## Hardware Requirements  

To set up and run **AdaptX**, the following hardware components are required:  

### **1. Core Processing Unit**  
- **Jetson Nano** – The main computing unit for running SLAM, object detection, and web-based control.  

### **2. Sensors & Perception**  
- **X2 RPLiDAR** – Used for real-time SLAM-based mapping and obstacle detection.  
- **Raspberry Pi V2 Camera** – Captures video feed for object detection using YOLO.  

### **3. Control & Actuation**  
- **Arduino** (e.g., Arduino Uno) – Handles motor control and sensor integration.  
- **L298N Motor Driver** – Controls the movement of the RC car.  
- **4-Wheel RC Car Chassis** – Serves as the initial test platform for AdaptX.  

### **4. Connectivity**  
- **WiFi Module** (ZEB-USB150WF1) – Enables wireless communication for the Flask-based web interface.  

### **5. Power Supply**  
- **Power Adapter (5V/4A for Jetson Nano)** – Required for stable operation.  
- **Battery Pack** (for RC Car and Peripherals) – Powers the motor driver and additional components.  

This hardware setup ensures **AdaptX functions efficiently** for **autonomous navigation, mapping, and real-time control**.  

## Software Requirements  

To run **AdaptX** smoothly, the following software dependencies and tools are required:  

### **1. Operating System & Environment**  
- **Ubuntu 18.04/20.04 (JetPack 4.x)** – Official NVIDIA Jetson Nano OS.  
- **Python 3.x** – Primary programming language for AI, SLAM, and web control.  

### **2. SLAM & Mapping**  
- **ROS (Robot Operating System) Melodic** – Required for integrating SLAM and sensor data processing.  
- **Hector SLAM** – Used for real-time LiDAR-based mapping.  

### **3. Object Detection**  
- **YOLO (You Only Look Once)** – Deep learning-based object detection framework.  
- **OpenCV** – Used for image processing and object detection.  

### **4. Web-based Control & Communication**  
- **Flask** – Web framework for controlling LiDAR, camera, and other processes remotely.  
- **Socket.IO** – Enables real-time communication between the web interface and backend.  

### **5. Peripheral & Hardware Control**  
- **Jetson.GPIO** – Required for handling GPIO pins on Jetson Nano.  
- **pySerial** – Enables communication between Jetson Nano and Arduino via serial.  

### **6. Additional Dependencies**  
- **NumPy, SciPy, Matplotlib** – Essential for data processing and visualization.  
- **Pip & Virtualenv** – Helps manage Python dependencies.

## Installation & Setup  

This section will guide you through setting up **AdaptX** on your **Jetson Nano**, installing necessary dependencies, and configuring the hardware components.  

### **1. Setting Up Jetson Nano**  
If you are new to Jetson Nano, follow the official NVIDIA guide to set up your device:  

🔗 [Getting Started with Jetson Nano](https://developer.nvidia.com/embedded/learn/get-started-jetson-nano-devkit)

### **2. Installing WiFi Driver**  

If you are using the **ZEB-USB150WF1 WiFi USB Mini Adapter** with **Jetson Nano**, you need to install a compatible driver.

For detailed instructions on installing the **ZEB-USB150WF1 WiFi USB Mini Adapter**, refer to the full guide:  

🔗 [WiFi Adapter Installation Guide](./WifiAdapter.md)

### **3.Installing ROS-Melodic on Jetson Nano**

For detailed instructions on installing ROS-Melodic on Jetson Nano, refer to the full guide:

[ROS-Melodic Installation Guide](ROS-Melodic.md)







 



