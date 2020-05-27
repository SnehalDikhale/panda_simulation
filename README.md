# Panda Simulation Environment (Gazebo + MoveIt!)

We placed a Franka Emika Panda Robot on a table in Gazebo and placed an object in front of it. The robot had a Realsense RS200 Camera attached to its wrist and a Panda Parallel Jaw Gripper. The Robot is controlled by MoveIt. 

## Installation

```
mkdir -p catkin_ws/src
cd catkin_ws/src
git clone https://github.com/SnehalD14/panda_simulation.git
git clone https://github.com/SnehalD14/panda_moveit_config.git
git clone --branch simulation https://github.com/SnehalD14/franka_ros.git
cd ..
sudo apt-get install libboost-filesystem-dev
rosdep install --from-paths src --ignore-src -y --skip-keys libfranka
cd ..
```
It is also important that you build the *libfranka* library from source and pass its directory to *catkin_make*  when building this ROS package as described in [this tutorial](https://frankaemika.github.io/docs/installation.html#building-from-source).

Build the catkin workspace and run the simulation:
```
catkin_make -j4 -DCMAKE_BUILD_TYPE=Release -DFranka_DIR:PATH=/path/to/libfranka/build
source devel/setup.bash
roslaunch panda_simulation simulation.launch
```

## Acknowledgement 

This is a modified and extended version of the work done by [erdalpekel](https://github.com/erdalpekel/panda_simulation)
