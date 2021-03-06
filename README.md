robot 
====
[![Build Status](https://travis-ci.org/ryugirou/robot.svg?branch=master)](https://travis-ci.org/ryugirou/robot)
## Install
```
cd ~/catkin_ws/src
git clone https://github.com/ryugirou/robot.git --recursive 
cd ~/catkin_ws
rosdep install --from-paths src --ignore-src
```
## Usage
gazebo上で動かすときはrobot_name:=omni4,実機で動かすときはrobot_name:=tr or pr
### 手動で動かす
```
roslaunch robot_control manual.launch robot_name:=tr
```

### 自動で動かす
```
roslaunch robot_control traj.launch robot_name:=pr
```

### laptopから動かす
```
ssh nhk@crs002.local
roscore
```
```
export ROS_IP=`hostname -I| cut -d' ' -f1`
export ROS_MASTER_URI=http://crs002.local:11311
export ROS_MASTER_URI=http://crs001.local:11311
```

## ボタン配置
pr/config/tasks.yaml,tr/config/tasks.yamlを参照

## Environment
| OS | ros | gazebo |
| ---------- | :--------: | --------: |
| ubuntu16.04 LTS  | kinetic | 7.15 |

## reference
[ROS講座](https://qiita.com/srs/items/5f44440afea0eb616b4a)
