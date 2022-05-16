# boat_movement
Ros package that implements my GPSDriver Scripts

I use Ros tools like catkin build  instead of catkin_make

Assuming you aready have a workspace and have sourced its bash file, you can use my package by running
$: catkin create pkg boat_movement --catkin-deps rospy roscpp std_msgs xacro move_base_msgs geometry_msgs

You should then be able to place this repository as a folder called "boat_movement" in the "src" folder of the desired 
ros_ws

It is intended for use with the VRX simulator. To use it with a real craft or other simluator, you may have to change
what msgs the scripts are publishing/subscribing to.


To follow are some plots of the right and left thrust command data vs time. I ran each test consecutive;y so the time axis is in seconds
but it doesn't start at zero, instead it starts at whenever I started the test from when I started rqt_plot.

This is a graph of gpsMove.py in action. As you can see, after it turns around, it rocks back and forth as each thruster is either sent a 1 or 0 command.
As time goes on, the craft will have less sway to it, unless an outside force were to mess up its course.
![gpsMoveGRAPH](https://user-images.githubusercontent.com/90875992/168690768-ea59a1a3-73ad-4db1-a309-01206c635dc8.png)


This is a plot of the PIVController.py running a similar test to what I ran for gpsMove. You can see it turn itself around before getting on course. It has some ocilation as well, but it is much smoother than gpsMove. I don't know why, but it didn't slow down as much as I expected once it got close to the target. 
![trajectoryMoveGRAPH1](https://user-images.githubusercontent.com/90875992/168691290-016b93f3-a12d-42b1-8b95-57fc9756cdc3.png)

I expected it to taper off as it got closer. Previous tests had plots similar to this one:
![pivGraphExpected](https://user-images.githubusercontent.com/90875992/168691289-42abfbfa-54c8-4dd0-86c9-f4a0b5631d57.png)


