MARC sim
=========

The marc_test package is for ROS simulation on Gazebo.  

|Author|Huang Tianjian|
|---|---
|E-mail|117010099@link.cuhk.edu.cn

****
## Structure of the package  

**urdf** file clip contains the urdf model file. Currently the package is using `smartcar.urdf.xacro`. `test.urdf.xacro` is an ackermann model on test.  
  
**config** file clip contains yaml files which stores parameters of ros controller.   
  
**launch** file clip contains launch files.  
  
**model** file clip contains other models needed, for example, the model of QR code "door". You can add any model in Gazebo world, depend on your private demands.    
  

## How to use  
To launch the simulation, use `roslaunch marc_test diff_smartcar.launch`.  
  
The launch file loads car model into Gazebo. Controller subscribes topic `/smartcar/diff_drive_controller/cmd_vel` as the velocity command. The model publics `/odom` and `/smartcar/camera1/image_raw` as odometry information and camera information. 
  
**Attention**: Currently, we provide a testing ackermann model `test.urdf.xacro`. No controller fits an ackermann model yet. However, the model itself works. You can check the model by running `view_demo.launch`. Before we finish our jobs, you can try to write a controller for this test model base on your own understanding.  
  
## Future work
The car model is a differential drive model because it is very difficult to realize an ackermann structure in Gazebo.  
  
There are two ways to improve:
  * Try another simulation software such as V-REP;
  * Continue to use Gazebo for ackermann structure development. That means a new controller should be developed.
    * About [ros_control](http://wiki.ros.org/ros_control);
    * About [ros controller](http://wiki.ros.org/ros_control/Tutorials/Writing%20a%20new%20controller);

  
## References 
https://github.com/parambeernegi/robot_arm_ros/tree/master/diff_drive


