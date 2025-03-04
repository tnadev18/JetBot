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


## Introduction

**AdaptX** is a modular autonomous system designed for seamless integration with various robotic platforms. Currently, it is being developed using a **4-wheel RC car** as a test platform to enable **autonomous navigation, real-time mapping, and object detection**.

Built on the **Jetson Nano** and powered by **X2 RPLiDAR, Raspberry Pi V2 Camera, and Arduino**, AdaptX leverages cutting-edge **AI and SLAM** technologies to achieve real-time perception and intelligent decision-making. The system provides a **web-based interface** using Flask, allowing users to remotely start and manage core processes such as **LiDAR-based mapping** and **camera-based object detection**. The live feed of both **object detection** and **Hector SLAM mapping** is accessible through the web interface, making AdaptX a versatile solution for robotics and automation applications.

This project serves as an **adaptable plug-and-play module** that can be integrated with different robotic platforms in the future, beyond the initial RC car testbed.


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



