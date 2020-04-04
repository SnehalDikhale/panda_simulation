# panda_simulation
Make sure you have installed libfranka for Panda

```
mkdir -p catkin_panda/src
cd catkin_panda/src
git clone https://github.com/SnehalD14/panda_simulation.git
git clone https://github.com/erdalpekel/panda_moveit_config.git
git clone https://github.com/SnehalD14/franka_ros.git
cd ..
sudo apt-get install libboost-filesystem-dev
rosdep install --from-paths src --ignore-src -y --skip-keys libfranka
cd ..
```
Build the catkin workspace and run the simulation:
```
catkin_make -j4 -DCMAKE_BUILD_TYPE=Release -DFranka_DIR:PATH=/path/to/libfranka/build
source devel/setup.bash
roslaunch panda_simulation simulation.launch
``` 
