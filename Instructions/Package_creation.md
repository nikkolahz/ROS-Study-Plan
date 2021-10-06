# Package Creation in ROS 
ROS applications are typically a compilation of packages with their own package manifest file and CMakeLists build file. 
These packaes are created using a catkin command to auto-generate these boilerplate files with other ros packages as an argument:
* Always source the setup.bash file whenever a new bash shell is opened
```
source /opt/ros/<ros-distro>/setup.bash
```
* Call the catkin command for package creation from within the workspace src folder
```
cd ~/catkin_ws/src
catkin_create_pkg <package_name> [depend1] [depend2] [depend3] 
```
example:
```
catkin_create_package myworkcell_core rospy roscpp std_msgs
```
The above command creates a package named: <b>myworkcell_core</b>.
This then automatically includes the dependecy packages <b>rospy, roscpp and std_msgs</b> in the manifests.
![alt-text](../images/package_creation.PNG?raw=True)
inside the created package.xml manifest:
![alt-text](../images/pkg_xml.PNG?raw=True)

## Common File structure:
