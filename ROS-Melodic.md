# Ubuntu Install of ROS Melodic  

We are building Debian packages for several Ubuntu platforms, listed below. These packages are more efficient than source-based builds and are our preferred installation method for Ubuntu. Note that there are also packages available from Ubuntu upstream. Please see [Upstream Packages](http://wiki.ros.org/UpstreamPackages) to understand the difference.  

## Installation  

### Supported Ubuntu Versions  
**ROS Melodic ONLY supports:**  
- **Ubuntu 18.04 (Bionic)**  
- **Debian 9 (Stretch)**  

---

## 1. Configure Your Ubuntu Repositories  
Ensure your Ubuntu repositories allow `"restricted," "universe," and "multiverse."` You can follow the [Ubuntu guide](https://help.ubuntu.com/community/Repositories/Ubuntu) for instructions.  

---

## 2. Setup Your Sources List  
Run the following command to add ROS package sources:  
```bash
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
