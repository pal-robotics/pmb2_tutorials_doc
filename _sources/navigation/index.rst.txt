# PMB-2 Navigation tutorial ROS2


## Purpose

This tutorial shows how to make PMB-2 navigate autonomously provided a map build up of laser scans and taking into account the laser and the RGBD camera in order to avoid obstacles.

## Pre-Requisites

First make sure that the tutorials are properly installed along with the PMB-2 simulation, as shown in the [Tutorials Installation](http://wiki.ros.org/Robots/PMB-2/Tutorials#Tutorials_Installation) Section. Then follow the instructions in the  [PMB2 mapping tutorial](https://cesc-folch.github.io/pmb2-tutorial/mapping) in order to create and save a map.

## Execution

First of all open two consoles and source PMB-2's public simulation workspace in each one
```
cd ~/pmb2_public_ws
source ./install/setup.bash
```
In the first console launch the following simulation
```
ros2 launch pmb2_2dnav_gazebo pmb2_navigation_gazebo.launch.py
```

This will launch a gazebo window and a rviz window with a map.
Select on the rviz window the `2D Pose Estimate` mode and set the approximate robot position on the map.

.. image:: media/pose_estimate.png
    :alt: rviz pose

![gazebo](media/gazebo_nav.png)

In the second console launch the keyboard teleoperation node
```
ros2 run teleop_twist_keyboard teleop_twist_keyboard --ros-args --remap cmd_vel:=key_vel
```

.. image:: media/key_teleop.png
    :alt: teleop ros2

Now you can navigate the robot to correct the position error.

To send a navigation goal you can use the rviz `Navigation2 Goal` mode and select the desired goal.

.. image:: media/goal.png
    :alt: gazebo goal

After selecting the goal you can see the global path planned and the local path.

.. image:: media/navigation.png
    :alt: navigation rviz
