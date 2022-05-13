# boat_movement
Ros package that implements my GPSDriver Scripts

I use Ros tools like catkin build  instead of catkin_make

Assuming you aready have a workspace and have sourced its bash file, you can use my package by running
$: catkin create pkg boat_movement --catkin-deps rospy roscpp std_msgs xacro move_base_msgs geometry_msgs

You should then be able to place this repository as a folder called "boat_movement" in the "src" folder of the desired 
ros_ws

It is intended for use with the VRX simulator. To use it with a real craft or other simluator, you may have to change
what msgs the scripts are publishing/subscribing to.
