.. _installation:

********************************
PMB-2 Installation tutorial ROS2
********************************


Purpose
#######

This tutorial shows how to install all the packages you need and set up a workspace to simulate PMB-2 navigation and mapping.

Installation
############

Install all the ros offical packages for pmb2.

.. code:: bash

   sudo apt update
   sudo apt install ros-foxy-pmb2*

Workspace
#########

We first create the directories for the workspace.

.. code:: bash

   mkdir -p ~/pmb2_public_ws/src
   cd ~/pmb2_public_ws/src


Then, inside the `src` folder we clone the following github repositories:

The `pmb2_simulation`_:

.. code:: bash

   git clone https://github.com/pal-robotics/pmb2_simulation.git
   cd pmb2_simulation
   git checkout foxy-devel
   cd ..

The `pal_gazebo_worlds`_:

.. code:: bash

   git clone https://github.com/pal-robotics/pal_gazebo_worlds.git
   cd pal_gazebo_worlds
   git checkout foxy-devel
   cd ..

After that we compile everything.

.. code:: bash

   colcon build

.. _pal_gazebo_worlds: https://github.com/pal-robotics/pal_gazebo_worlds
.. _pmb2_simulation: https://github.com/pal-robotics/pmb2_simulation
