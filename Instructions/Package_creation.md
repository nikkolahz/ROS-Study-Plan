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
  ![alt-text](../images/package_creation.PNG?raw=True)</br>
Inside the created package.xml manifest:  
  ![alt-text](../images/pkg_xml.PNG?raw=True)  
Inside the created CMakeLists.txt local to the package:  
  ![alt-text](../images/pkg_makefile.PNG?raw=True)  
Scripts and codes can now be created inside the package's src folder.  

# Build a package
To build a package, make sure that local setup.bash file in the workspace is sourced:  
```
source ~/catkin_ws/devel/setup.bash
```
Then go back to the root workspace directory:   
```
cd ~/catkin_ws
```
Perform catkin build command:
```
catkin build
```
If everything is okay, required dependencies will be downloaded and all packages will be built.  
To continue running the buils application, make sure to perform local source command again:  
```
source ~/catkin_ws/devel/setup.bash

```
Screenshot is found here:  
![alt-text](../images/package_build.PNG?raw=True)  
As shown, a success message will be displayed if everything is fine.  
