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
```

## 3. Set Up Your Keys  
To ensure secure downloads from the ROS repository, set up your system keys:  

```bash
sudo apt install curl  # If curl isn't installed
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
```

## 4. Installation
First, make sure your Debian package index is up-to-date:

```bash
sudo apt-get update
```

First, make sure your Debian package index is up-to-date:
```bash
sudo apt-get update
```

There are many different libraries and tools in ROS. We provided four default configurations to get you started. You can also install ROS packages individually.

In case of problems with the next step, you can use following repositories instead of the ones mentioned above: ros-shadow-fixed

### Installation Options

1. **Desktop-Full Install: (Recommended)**
   ROS, rqt, rviz, robot-generic libraries, 2D/3D simulators, navigation and 2D/3D perception
   ```bash
   sudo apt-get install ros-melodic-desktop-full
   ```

2. **Desktop Install:**
   ROS, rqt, rviz, and robot-generic libraries
   ```bash
   sudo apt-get install ros-melodic-desktop
   ```

3. **ROS-Base: (Bare Bones)**
   ROS package, build, and communication libraries. No GUI tools.
   ```bash
   sudo apt-get install ros-melodic-ros-base
   ```

4. **Individual Package:**
   You can also install a specific ROS package (replace underscores with dashes of the package name):
   ```bash
   sudo apt-get install ros-melodic-PACKAGE
   
   # Example:
   sudo apt-get install ros-melodic-slam-gmapping
   ```

To find available packages, use:
```bash
apt-cache search ros-melodic
```

## 5.Environment Setup
It's convenient if the ROS environment variables are automatically added to your bash session every time a new shell is launched:

```bash
echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

*If you have more than one ROS distribution installed, ~/.bashrc must only source the setup.bash for the version you are currently using.*

If you just want to change the environment of your current shell, instead of the above you can type:
```bash
source /opt/ros/melodic/setup.bash
```

### Zsh Setup
If you use zsh instead of bash you need to run the following commands to set up your shell:
```bash
echo "source /opt/ros/melodic/setup.zsh" >> ~/.zshrc
source ~/.zshrc
```

## 6.Dependencies for Building Packages
To create and manage your own ROS workspaces, install these tools and dependencies:
```bash
sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential
```

## 7.Initialize rosdep
Before you can use many ROS tools, you will need to initialize rosdep. 

Install rosdep:
```bash
sudo apt install python-rosdep
```

Initialize rosdep:
```bash
sudo rosdep init
rosdep update
```

## 8.Build Farm Status
The packages that you installed were built by the ROS build farm.

Now as you have installed ROS-Melodic, its time to set and configure ROS Environment.

# Installing and Configuring Your ROS Environment

## Managing ROS Melodic Environment

## Environment Setup

During the installation of ROS, you will see that you are prompted to source setup.*sh files. ROS relies on combining spaces using the shell environment, which makes developing against different versions or sets of packages easier.

### Checking ROS Environment

To verify your ROS environment is properly set up, check the ROS-related environment variables:

```bash
$ printenv | grep ROS
```

If no variables are shown, you might need to source the setup files.

### Environment Setup Files

Environment setup files can come from different sources:
- ROS packages installed with package managers
- rosbuild workspaces
- Catkin packages (build or installation by-products)

**Note:** In modern ROS, catkin is the recommended method for organizing and building code, using standard CMake conventions and providing more flexibility.

### Sourcing Setup Files

If you installed ROS from apt on Ubuntu, you can source the setup files like this:

```bash
$ source /opt/ros/melodic/setup.bash
```

You'll need to run this command on every new shell or add it to your `.bashrc` to have consistent ROS access. This allows installing multiple ROS distributions on the same computer.

## Create a ROS Workspace

Let's create and build a catkin workspace:

```bash
$ mkdir -p ~/catkin_ws/src
$ cd ~/catkin_ws/
$ catkin_make
```

The `catkin_make` command is a convenience tool for working with catkin workspaces. Running it the first time will create a CMakeLists.txt link in your 'src' folder.

### Python 3 Compatibility (ROS Melodic)

For Python 3 users, use this first catkin_make command:

```bash
$ catkin_make -DPYTHON_EXECUTABLE=/usr/bin/python3
```

This configures catkin_make with Python 3. Subsequent builds can use standard `catkin_make`.

### Workspace Structure

After running `catkin_make`, you'll see:
- 'build' folder
- 'devel' folder with several setup.*sh files

Source the new setup file:

```bash
$ source devel/setup.bash
```

Verify the workspace is correctly overlayed:

```bash
$ echo $ROS_PACKAGE_PATH
/home/youruser/catkin_ws/src:/opt/ros/melodic/share
```

### Additional Notes

- This approach works for ROS Groovy and later
- For earlier versions (ROS Fuerte and before), use rosbuild

## Best Practices

- Always source the appropriate setup file
- Create separate workspaces for different projects
- Use `catkin_make` for building your workspace
- Check environment variables if you encounter package-related issues



