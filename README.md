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



