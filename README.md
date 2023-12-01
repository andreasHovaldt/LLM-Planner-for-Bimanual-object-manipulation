# LLM-Planner-for-Bimanual-object-manipulation
Robotics 5th semester project. LLM planner for Bimanual object manipulation using ChatGPT, YoloV8 and the Robotiq 3F adaptive gripper.

## Required libraries/software

### Python3
```shell
pip install open3d
pip install ultralytics
pip install pymodbus
```

## Quick Start
Install [ROS2 Humble](https://docs.ros.org/en/humble/Installation.html), [colcon](https://docs.ros.org/en/humble/Tutorials/Colcon-Tutorial.html#install-colcon), [rosdep](https://docs.ros.org/en/crystal/Installation/Linux-Install-Binary.html#installing-and-initializing-rosdep) and [vcstool](https://github.com/dirk-thomas/vcstool#how-to-install-vcstool). Build this repository

```shell
mkdir -p LLM-Bimanual-Planner/src && cd LLM-Bimanual-Planner
wget https://raw.githubusercontent.com/andreasHovaldt/LLM-Planner-for-Bimanual-object-manipulation/main/repos.yaml -P src
wget https://raw.githubusercontent.com/andreasHovaldt/LLM-Planner-for-Bimanual-object-manipulation/main/config -P src
vcs import src < src/repos.yaml
rosdep install --from-paths src --ignore-src -r -y
colcon build --symlink-install
```
Next, download 'terminator' and change the config file (found in ~/.config/terminator/config) to the one found in this repository.

```shell
sudo apt install terminator
mv ~/.config/terminator/config ~/.config/terminator/old_config && mv src/config ~/.config/terminator/config
```
Now, while running the LBRServer program on the KUKAs, start the robot with the following command:

```shell
terminator -l Launch
```

OBS: It is important that the two KUKA IIWA 7s are configured with different ports. Follow the robot setup guide from [LBR-stack](https://lbr-fri-ros2-stack-doc.readthedocs.io/en/humble/lbr_fri_ros2_stack/lbr_fri_ros2_stack/doc/robot_setup.html).
