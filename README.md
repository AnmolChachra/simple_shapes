# simple_shapes ROS package
This ROS package contains a ROS node that allows for a simple following of a regular polygon based on number of sides, distance and velocities. You can also switch between clockwise and anticlockwise motion. It also calculates and publishes the error between practical and theoretical positions at each vertex and controls can be adjusted to minimize this.

## Requirements
<ul><li>ROS -- tested on Melodic, but other versions may work
  </li><li>catkin_make -- used for building the application</li></ul>

## Build
Once cloned in a ROS workspace, e.g. `vnc-ross/workspace/src`, run the following commands to build it:
```
cd vnc-ross
catkin_make
```
## Run
<b>Step 1:</b> Run rosmaster by running the simulator. We use turtlebot3_gazebo for testing. You can download the package and launch it as follows. (Note: You can use a different world or package)
```
sudo apt-get install ros-melodic-turtlebot3-gazebo
roslaunch turtlebot3_gazebo turtlebot3_empty_world.launch
```
<b>Step 2:</b> Open your browser to `localhost:8080/vnc.html` and click connect.<br><br>
<b>Step 3:</b> Make sure you have built the package so it is accessible from any directory location. Run the following command
```
rosrun simple_shapes simple_shapes
```
If you don't want to build the package, you can still run it as follows
```
cd vnc-ross/workspace/src
rosrun simple_shapes simple_shapes
```
Now, checkout the browser to see your robot make a clockwise hexagon (default)<br><br>
<b>Step 4 (Optional):</b> This package gives you flexibility to control the following attributes
```
'/simple_shapes/n' - (INT) define the sides of the regular polygon (default 6)
'/simpe_shapes/l' - (INT) define the length of each side/distance between two vertices (default 1)
'simple_shapes/clockwise' - (INT) define whether to move clockwise or anticlockwise (default clockwise)
```
Before running command in <b>Step 3</b>, you can set the aforementioned parameters in the terminal as follows:
```
# For triangle anticlockwise
rosparam set /simple_shapes/n 3
rosparam set /simple_shapes/l 1
rosparam set /simple_shapes/clockwise 0
```


