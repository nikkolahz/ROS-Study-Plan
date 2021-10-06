## ROS Nodes  
>&nbsp;&nbsp;A node is **a process that performs computation**. Nodes are combined together into a graph and communicate with one another using streaming topics, RPC services, and the Parameter Server. These nodes are **meant to operate at a fine-grained scale**; a robot control system will usually comprise many nodes. For example, one node controls a laser range-finder, one Node controls the robot's wheel motors, one node performs localization, one node performs path planning, one node provides a graphical view of the system, and so on.  
  &nbsp;&nbsp;The use of nodes in ROS provides several benefits to the overall system. There is **additional fault tolerance** as crashes are **isolated to individual nodes**. Code **complexity is reduced** in comparison to monolithic systems. Implementation details are also well hidden as the nodes   expose a **minimal API to the rest of the graph** and alternate implementations, even in other programming languages, can easily be substituted.   
  &nbsp;&nbsp;All running nodes have a **graph resource name** that uniquely identifies them to the rest of the system. For example, /hokuyo_node could be the name of a Hokuyo driver broadcasting laser scans. Nodes also have a **node type**, that simplifies the process of referring to a node executable on the fileystem. These **node types are package resource names** with the name of the node's package and the name of the node executable file. In order to resolve a node type, ROS searches for all executables in the package with the specified name and chooses the first that it finds. As such, you need to ***be careful and not produce different executables with the same name in the same package***.  
A ROS node is written with the use of a ROS client library, such as roscpp or rospy.  
-- ROS.org [link](http://wiki.ros.org/Nodes)  


### `rosnode` is a command-line tool to extensively fetch information about Nodes.

* rosnode info
* rosnode kill
* rosnode list
* rosnode machine
* rosnode ping
* rosnode cleanup
```
rosnode info <node-name>
rosnode kill <node-name1> <another-node>  # Can kill multiple nodes
rosnode list
rosnode machine <machine-name> # Lists nodes on a machine e.g. ninja.local
rosnode ping <node-name> 
rosnode cleanup # Not advised to be used in normal operation
```
A more detailed discussion is found [here](http://wiki.ros.org/Nodes).

## Messages  
```
This is a sample multi0line code block
```
## Services  
```
This is a sample multi0line code block
```
## Launching Applications  
```
This is a sample multi0line code block
```
## Visualizations and Simulations
```
This is a sample multi0line code block
```
Back in [Main](../README.md)
