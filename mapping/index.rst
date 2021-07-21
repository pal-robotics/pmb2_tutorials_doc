***************************
PMB-2 Mapping tutorial ROS2
***************************


Purpose
#######

This tutorial shows how to make PMB-2 navigate and create a map using the navigation from ros2. You can find further information about that in the [nav2 SLAM tutorial](https://navigation.ros.org/tutorials/docs/navigation2_with_slam.html).

Pre-Requisites
##############

First make sure that the tutorials are properly installed along with the PMB-2 simulation, as shown in the [Tutorials Installation](http://wiki.ros.org/Robots/PMB-2/Tutorials#Tutorials_Installation) Section.

Execution
#########

First of all open two consoles and source PMB-2's public simulation workspace in each one
```
cd ~/pmb2_public_ws
source ./install/setup.bash
```
In the first console launch the following simulation
```
ros2 launch pmb2_2dnav_gazebo pmb2_mapping_gazebo.launch.py
```
.. image:: media/gazebo.png
    :alt: gazebo mapping

Note that a rviz will also show up in order to visualize the mapping process.

.. image:: media/rviz_map.png
    :alt: rviz mapping

In the second console launch the keyboard teleoperation node
```
ros2 run teleop_twist_keyboard teleop_twist_keyboard --ros-args --remap cmd_vel:=key_vel
```

You can use the keyboard to navigate the robot and create the map.

.. image:: media/key_teleop.png
    :alt: teleop ros2

As shown in the [nav2 SLAM tutorial](https://navigation.ros.org/tutorials/docs/navigation2_with_slam.html) you can save the map by doing:

```
ros2 run nav2_map_server map_saver_cli -f ~/map
```
