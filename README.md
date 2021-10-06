# ROS-Study-Plan
>Study Plan for use of Robotics Operating System ROS

## Elementary concepts 
* [C++](https://www.micc.unifi.it/bertini/download/programmazione/TICPP-2nd-ed-Vol-one-printed.pdf)<br/>
* [python](https://www.youtube.com/playlist?list=PLjgj6kdf_snaw8QnlhK5f3DzFDFKDU5f4)<br/>
* [Robot kinematics and concepts](https://www.youtube.com/playlist?list=PLggLP4f-rq02vX0OQQ5vrCxbJrzamYDfx)<br/>
## ROS
> The Robot Operating System ([ROS](https://www.ros.org/)) is a flexible framework for writing robot software. It is a collection of tools, libraries, and conventions that aim to simplify the task of creating complex and robust robot behavior across a wide variety of robotic platforms. <br/>
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
### 2. Core concepts
> We will be setting up environment for ROS in Ubuntu OS on a PC.
#### 2.a. ROS PC Setup <br/>
> It is advisable to have a running Ububtu OS on the PC rather than a virtual box due to some performance limitations. This can be done by dual booting. However, some tutorials like that in ROS industrial has available virtual images (can be run in Oracle Virtualbox) which can be used for training.
  * Setup the sources.list and setting up the keys:
  ```
  sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
  sudo apt install curl # if you haven't already installed curl
  curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
  ```
  * Making sure debian packga index is updated:
  ```
  sudo apt update
  ```
  * Installing the required variant: Replace <ros-distro> with the appropriate version ex: noetic/melodic. Always check compatibility with ubutu version!!
  ```
  #Full desktop install with Visualization tools (recommended)
    sudo apt install ros-<ros-distro>-desktop-full 
  
  # Minimal Desktop version
    sudo apt install ros-melodic-desktop

  # Bare-bones with no GUI
    sudo apt install ros-melodic-ros-base
  
  # individual package: Replace PACKAGE with vaid package names
    sudo apt install ros-melodic-PACKAGE
  ```
2.b. Environment configuration <br/>
  * Sourcing the setup.bash foe use in the bash session. Note: Replace <ros-distro> with correct installed version: e.g. noetic, melodic etc.
  ```
  echo "source /opt/ros/<ros-distro>/setup.bash" >> ~/.bashrc
  source ~/.bashrc
  ```
  * To change environment of current shell:
  ```
  ource /opt/ros/<ros-distro>/setup.bash
  ```
`$ sudo apt install <some cool linux scripts here>` <br/>
2.c. Catkin work space and packages <br/>
`$ sudo apt install <some cool linux scripts here>` <br/>
2.d. Messages and Topics<br/>
```
$<multi-lin codes>
$<multi-lin codes>
$<multi-lin codes>
```
2.e. File Structure </br>
```
$<multi-lin codes>
$<multi-lin codes>
$<multi-lin codes>
```
2.f. Launching complex applications </br>
```
$<multi-lin codes>
$<multi-lin codes>
$<multi-lin codes>
```
2.g. Visualizations </br>
```
$<multi-lin codes>
$<multi-lin codes>
$<multi-lin codes>
```
### 3. Commonly used packages and use cases
3.a. move_group </b>
3.b. rviz? </b>
3.c. moveit? </b>
3.d. tf </b>

### 4. Modeling custom robots
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
