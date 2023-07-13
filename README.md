# PiCarSLAM

## Project Overview:

_TBD_

## Installation Requirements

* _ROS Version_ Required: Noetic

* Make sure that _Gazebo_ and _Rviz_ are installed:

$ sudo apt-get install ros-noetic-gazebo-ros-pkgs ros-noetic-gazebo-ros-control

$ sudo apt-get install ros-kinetic-rviz

* _Python version_: Python3 or more. To avoid conflicts with previous versions: $ sudo apt install python-is-python3

## Installation Steps

1. In the Home folder ($ cd ~) create the **catkin_ws** folder:

$ mkdir -p ~/picar_ws/src

2. **Clone** the repository in the folder "src":

$ cd ~/picar_ws/src

$ git clone https://github.com/matteomastrogiuseppe/PiCarSLAM 

3. **Build** the workspace and packages:

$ cd ~/picar_ws

$ catkin_make

4. Add the following lines at the end of the **/.bashrc file** (basically after the last "fi"):

$ gedit ~/.bashrc _(to open and edit)_

"source /opt/ros/noetic/setup.bash

source ~/picar_ws/devel/setup.bash

export GAZEBO_MODEL_PATH=~/picar_ws/src/car_model/models:$GAZEBO_MODEL_PATH"

5. Source the ./bashrc file:

$ source ~/.bashrc

## Run the simulation:

To launch the car_model in Gazebo (main simulation):

$ roslaunch car_model gazebo.launch

To launch the car_model in RViz (lighter):

$ roslaunch car_model twist_driver.launch
 
To launch the keyboard controller:

$ rosrun teleop_twist_keyboard teleop_twist_keyboard.py
