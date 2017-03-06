# Piaggio Fast Forward ROS Test

## Introduction
This package was built with ROS Indigo. I acknowledge that the test was supposed to be done in ROS Kinetic Kame, but for lack of time, the package was built using the platform already available to me which was ROS Indigo. 

The package contains the following:

1. URDF description of a differential drive robot (urdf/pff\_diff\_drive.urdf)
   
   For lack of time, this URDF was obtained from [this repository](https://github.com/qboticslabs/mastering\_ros/blob/master/chapter\_2\_codes/mastering\_ros\_robot\_description\_pkg/urdf/diff\_wheeled\_robot.urdf)
2. Launch files: (launch/)
   - **display.launch** The launch file used to launch the visualization of the robot in RVIZ
     
     _Usage:_ `roslaunch pff_diff_drive display.launch`
   - **gazebo.launch** The launch file used to launch the robot in the Gazebo simulator
     
     _Usage:_ 1. **Keyboard teleop mode:** `roslaunch pff_diff_drive gazebo.launch key_teleop:=true`

       Please note: A new window (terminal) opens when `key_teleop` is set to true. The keyboard input needs to be given with this new terminal being active. If this new terminal is inactive, no commands would be given to the node and the robot would not move. To ensure that the new terminal is active, please click anywhere inside the terminal. Once active, pressing any arrow key will translate to the appropriate velocity and publish to `/cmd_vel`

     _Usage:_ 2. **Circle mode:** `roslaunch pff_diff_drive gazebo.launch circle_switch:=true diameter:=2.0`

     The diameter is to be specified in meters and can be set to the desired value, but defaults to 1.0 meter if not set

     _Usage:_ 3. **Square mode:** `roslaunch pff_diff_drive gazebo.launch square_switch:=true side:=2.0`

     The side is to be specified in meters and can be set to the desired value, but defaults to 1.0 meter if not set.

     The square mode is not perfect. There are errors that accumulate over time because it has been implemented by simply publishing to the `/cmd_vel` topic.

     In the ideal case, we would need to create an action server and client or use the existing `move_base` action server to send specific goals in order to achieve a more consistent square pattern.

3. Scripts: (scripts/)
   - **drive_in_circles.py** The script that is launched when the `circle_switch` parameter is enabled when launching `gazebo.launch`

      This script publishes `geometry_msgs/Twist` messages to `/cmd_vel` in an appropriate way so as to achieve a circular pattern with a diameter as specified by the `diameter` parameter.

   - **drive_in_squares.py** The script that is launched when the `square_switch` parameter is enabled when launching `gazebo.launch`

      This script publishes `geometry_msgs/Twist` messages to `/cmd_vel` in an appropriate way so as to achieve an almost square pattern with side as specified by the `side` parameter.

   - **keyboard_teleop.py** This script enables publishing to `/cmd_vel` using the arrow keys in the keyboard when the `key_teleop` parameter in gazebo.launch is set to true. This script was obtained from [here](https://github.com/bmagyar/key_teleop/tree/master/scripts) for lack of time.

4. Rviz configuration (rviz/pff_diff_drive.rviz)
   
   Configuration for RVIZ visualizer.

## Author
Kiran Mohan

Robotics Engineering Intern

Fetch Robotics

Email: kmohan@wpi.edu
