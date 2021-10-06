![alt-text](https://github.com/nikkolahz/ROS-Study-Plan/blob/main/images/ros.png?raw=True)</br>
# Study Plan
Study Plan for use of Robotics Operating System ROS 
The objective of this is to collate the basic instructions and references for learning the ins and outs of the ROS platform:  
* [Elementary concepts](#elementary-concepts)
* [Compatibilities and distros](#1-compatibilities-and-distributions)
* [PC setup](#2-ros-pc-setup)
* [ROS core concepts](#3-ros-core-concepts)
* [Commonly used packages](#4-common-packages)
* [Robot Modelling](#5-modeling-custom-robots)
* [Robot Simulation]
* [Use Cases]  
> Before robot operating systems, every robot designer and robotics researcher would spend considerable amounts of time designing the embedded software within a robot, as well as the hardware itself. This required skills in mechanical engineering, electronics and embedded programming. Typically, the programs engineered in this way were more akin to embedded programming, similar to electronics, than they were to robotics in the strictest sense, such as we might encounter it nowadays in service robotics. There was considerable re-use of programs, as they were strongly linked to the underlying hardware.  
The main idea of a robotics OS is to avoid continuously reinventing the wheel, and to offer standardised functionalities performing hardware abstraction, just like a conventional OS for PCs, hence the analogous name.  
--Source: generationrobots.com [article](https://www.generationrobots.com/blog/en/ros-robot-operating-system-2/)

## Elementary concepts 
* [C++](https://www.micc.unifi.it/bertini/download/programmazione/TICPP-2nd-ed-Vol-one-printed.pdf)<br/>
* [python](https://www.youtube.com/playlist?list=PLjgj6kdf_snaw8QnlhK5f3DzFDFKDU5f4)<br/>
* [Robot kinematics and concepts](https://www.youtube.com/playlist?list=PLggLP4f-rq02vX0OQQ5vrCxbJrzamYDfx)<br/>
## ROS
The Robot Operating System ([ROS](https://www.ros.org/)) is a flexible framework for writing robot software. It is a collection of tools, libraries, and conventions that aim to simplify the task of creating complex and robust robot behavior across a wide variety of robotic platforms. <br/>
### 1. Compatibilities and [Distributions](http://wiki.ros.org/Distributions)
#### ROS 2:<br/>
* Noetic <br/>
* Melodic <br/>
#### ROS 1: <br/>
* Lunar <br/>
* Kinetic <br/>
* Jade <br/>
* Indigo <br/>
* Hydro <br/>

Other compatibility details are available [here](https://www.ros.org/reps/rep-0003.html). <br/>
### 2. ROS PC Setup
 It is advisable to have a running Ubuntu OS on the PC rather than a virtual box due to some performance limitations. This can be done by dual booting. However, some tutorials like that in ROS industrial has available virtual images (can be run in Oracle Virtualbox) which can be used for training.  

  * Setup the sources.list and setting up the keys:
  ```
  sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
  sudo apt install curl # if you haven't already installed curl
  curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
  ```
  * Making sure debian package index is updated:
  ```
  sudo apt update
  ```
  * Installing the required variant: Replace `<ros-distro>` with the appropriate version ex: noetic/melodic. Always check compatibility with ubutu version!!
  ```
  #Full desktop install with Visualization tools (recommended)
    sudo apt install ros-<ros-distro>-desktop-full 
  
  # Minimal Desktop version
    sudo apt install ros-<ros-distro>-desktop

  # Bare-bones with no GUI
    sudo apt install ros-<ros-distro>-ros-base
  
  # individual package: Replace PACKAGE with vaid package names
    sudo apt install ros-<ros-distro>-PACKAGE
  ```

#### 2.a. Environment configuration <br/>

  * Sourcing the setup.bash foe use in the bash session. Note: Replace `<ros-distro>` with correct installed version: e.g. noetic, melodic etc.
  ```
  echo "source /opt/ros/<ros-distro>/setup.bash" >> ~/.bashrc
  source ~/.bashrc
  ```
  * To change environment of current shell:
  ```
  source /opt/ros/<ros-distro>/setup.bash
  ```
 * Installing package dependencies that might be needed in your development
 ```
 #This command installs the packages: python-rosdep; python-rosinstall-generator etc.
  sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential
 ```
 * Initialize rosdep. This is a command-line tool for installing system dependencies
 ```
 sudo rosdep init
 rosdep update
 ```
 At this point your environment should be ready. If some troubles are encountered in setting up, check the tutorial steps in this [link](http://wiki.ros.org/melodic/Installation/Ubuntu). </br>

#### 2.b. Catkin work space and packages <br/>
 * Creating a workspace. Note: Replace `<ros-distro>` with the appropriate version ex: noetic/melodic.
  ```
  # First source youor setup.bash
  source /opt/ros/<ros-distro>/setup.bash
 
  # Create a catkin workspace
  mkdir -p ~/catkin_ws/src
  cd ~/catkin_ws/
  catkin_make
  ```
 ![alt-text](images/catkin_make1.PNG?raw=True)  
 You shoud be able to confirm that workspace is initialized with 'build' and 'devel' folders.  
 ![alt-text](images/catkin_make2.PNG?raw=True)  
 * Source your new local bash file for properly overlaying the current workspace.
  ```
  source devel/setup.bash
  ```
 * Creating a catkin package:
 The catkin workspace file structure is: 
 ```
 catkin_ws/
  src/
    CMakeLists.txt
    package_1/
      CMakelists.txt   # This is a local CMake file
      package.xml      # Local package manifest
      src/
       some_program.cpp
       some_program.py
      srv/
       some_service_files.srv
      support/
       some_launch_file.launch
      urdf/
       some_robot_models.urdf
       some_robot_models.xacro
     config/
 
 ....
    package_2/
      CMakeLists.txt
      package.xml
    src/
    ....
 ```
### 2.c.Creating a package  
Packages are the basic components of a ROS application. Instructions for package creation is found [here](/Instructions/Package_creation.md).    
 
## 3. ROS Core concepts  
* [ROS Nodes](/Instructions/Core_concepts.md#ros-nodes)
* [Messages](/Instructions/Core_concepts.md#messages)
* [Services](/Instructions/Core_concepts.md#services)
* [Launching Applications](/Instructions/Core_concepts.md#launching-applications)
* [Visualizations and Simulation](/Instructions/Core_concepts.md#visualizations-and-simulations)
### 4. Common Packages
3.a. move_group </b>
3.b. rviz? </b>
3.c. moveit? </b>
3.d. tf </b>

### 5. Modeling custom robots
4.a. Frames, links and joints </br>
* MIT Resource explaination. ([link](https://ocw.mit.edu/courses/mechanical-engineering/2-12-introduction-to-robotics-fall-2005/lecture-notes/chapter3.pdf)).</br>
* Yoskawa Glossary of Robot terms ([link](https://www.motoman.com/en-us/about/company/robotics-glossary)). </br>

4.b. URDF </br>
4.c. xacro </br>
4.d. Launching to rViz </br>
4.e. Launching to gazebo </br>
4.f. Controllers </br>
4.g. Config files


## ROS Industrial [site](https://industrial-training-master.readthedocs.io/en/melodic/)
* Follow the tutorials [here](https://industrial-training-master.readthedocs.io/en/melodic/)
* Virtual box training images [here](https://rosi-images.datasys.swri.edu/).
* Official github repository of exercises[here](https://github.com/ros-industrial/industrial_training/tree/foxy/exercises).

## Reading List Topics
* Motion Planning </br>
* Controllers </br>
* Modeling in Blender and file conversions for gazebo simulation </br>
* API creation</br>
* Supported communication networks in ROS? </br>
* Sensors simulation </br>
* Force Torques sensing </br>

## Interesting use-cases:
* Multi -robot systems (swarm robotics) ? </br>
* Collaborative Robotics </br>
* Integration with Machine Vision and deep learning </br>
* Simultaneous Localization and Mapping </br>
