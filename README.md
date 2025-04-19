# TurtleBot4 Setup & Simulation Guide

This repository provides a comprehensive guide to set up TurtleBot4 simulation, SLAM, teleoperation, and multi-robot environments using ROS 2 Humble and Ignition Fortress. It also covers 3D mapping using RTAB-Map.

---

## 🛠️ Installation

### TurtleBot4 Simulator

```bash
sudo apt install ros-humble-turtlebot4-simulator ros-humble-irobot-create-nodes
sudo apt install ros-dev-tools
```

### Ignition Fortress

```bash
sudo apt-get update && sudo apt-get install wget
sudo sh -c 'echo "deb http://packages.osrfoundation.org/gazebo/ubuntu-stable $(lsb_release -cs) main" > /etc/apt/sources.list.d/gazebo-stable.list'
wget http://packages.osrfoundation.org/gazebo.key -O - | sudo apt-key add -
sudo apt-get update && sudo apt-get install ignition-fortress
```

---

## 🚀 Running the Simulator

### Default Launch

```bash
ros2 launch turtlebot4_ignition_bringup turtlebot4_ignition.launch.py
```

### Launch with SLAM and Nav2

```bash
ros2 launch turtlebot4_ignition_bringup turtlebot4_ignition.launch.py slam:=true nav2:=true rviz:=true
```

---

## 🕹️ Teleoperation

### Install Teleop Twist Keyboard

```bash
sudo apt install ros-humble-teleop-twist-keyboard
```

### Run Teleop

```bash
ros2 run teleop_twist_keyboard teleop_twist_keyboard
```

---

## 🗺️ SLAM and Visualization

### Install TurtleBot4 Navigation

```bash
sudo apt install ros-humble-turtlebot4-navigation
```

### Launch SLAM and RViz

```bash
ros2 launch turtlebot4_navigation slam.launch.py
ros2 launch turtlebot4_viz view_robot.launch.py
```

---

## 🤖 Multi-Robot Simulation

```bash
# Launch robot1
ros2 launch turtlebot4_ignition_bringup turtlebot4_ignition.launch.py namespace:=/robot1 nav2:=true slam:=false localization:=true rviz:=true

# Spawn robot2
ros2 launch turtlebot4_ignition_bringup turtlebot4_spawn.launch.py namespace:=/robot2 x:=0.0 y:=1.0 nav2:=true slam:=false localization:=true rviz:=true
```

---

## 🧠 3D Mapping with RTAB-Map

```bash
ros2 launch rtabmap_launch rtabmap.launch.py
```

Make sure the camera and TF tree are properly set up before launching RTAB-Map.

---

## ✅ Requirements

- Ubuntu 22.04
- ROS 2 Humble Hawksbill
- Ignition Fortress

---

## 📌 Notes

- Always source your ROS environment before running any commands:
  ```bash
  source /opt/ros/humble/setup.bash
  ```

---

Feel free to contribute or raise issues if you face any trouble!
