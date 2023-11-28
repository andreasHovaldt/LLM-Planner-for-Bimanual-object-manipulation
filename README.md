# LLM-Planner-for-Bimanual-object-manipulation
Robotics 5th semester project. LLM planner for Bimanual object manipulation using ChatGPT, YoloV8 and the Robotiq 3F adaptive gripper.

## Quick Start
Install [colcon](https://docs.ros.org/en/humble/Tutorials/Colcon-Tutorial.html#install-colcon), [rosdep](https://docs.ros.org/en/crystal/Installation/Linux-Install-Binary.html#installing-and-initializing-rosdep) and [vcstool](https://github.com/dirk-thomas/vcstool#how-to-install-vcstool). Build this repository

```shell
mkdir -p LLM-Bimanual-Planner/src && cd LLM-Bimanual-Planner
wget https://raw.githubusercontent.com/andreasHovaldt/LLM-Planner-for-Bimanual-object-manipulation/main/repos.yaml -P src
vcs import src < src/repos.yaml
rosdep install --from-paths src --ignore-src -r -y
colcon build --symlink-install
```
