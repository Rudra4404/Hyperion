# 🗺️ Mapping with TurtleBot4

This project uses **TurtleBot4** to perform SLAM (Simultaneous Localization and Mapping) and generate 2D maps using ROS 2. It demonstrates how to launch mapping using the `slam_toolbox`, teleoperate the robot, and save the map.

---

## 🛠️ Requirements

- **TurtleBot4** (Lite or Standard)
- **ROS 2** (Humble or newer)
- `slam_toolbox`
- `teleop_twist_keyboard` (for manual control)
- A computer connected to the same network as TurtleBot

---

## 🚀 Setup

### 1. Install Required Packages

```bash
sudo apt update
sudo apt install ros-humble-slam-toolbox ros-humble-teleop-twist-keyboard
```

> Replace `humble` with your ROS 2 distro if different.

---

## 📡 Connecting to TurtleBot4

SSH into TurtleBot4:

```bash
ssh ubuntu@<TURTLEBOT4_IP>
```

Source the ROS setup:

```bash
source /opt/ros/humble/setup.bash
source ~/turtlebot4_ws/install/setup.bash
```

---

## 🧭 Launch SLAM

On TurtleBot4:

```bash
ros2 launch turtlebot4_navigation slam.launch.py
```

---

## 🎮 Teleoperate the Robot

On your laptop:

```bash
ros2 run teleop_twist_keyboard teleop_twist_keyboard
```

Use the keyboard to move the robot and build the map.

---

## 💾 Save the Map

Once the map is complete:

```bash
ros2 run nav2_map_server map_saver_cli -f ~/my_map
```

This will save `my_map.yaml` and `my_map.pgm` in your home directory.

---

## 🗂️ Folder Structure

```
turtlebot4_mapping/
├── launch/
│   └── mapping.launch.py
├── maps/
│   └── my_map.yaml / .pgm
├── README.md
└── ...
```

---

## 📸 Example Output

![Map Screenshot](https://raw.githubusercontent.com/yourusername/turtlebot4_mapping/main/maps/sample_map.png)

---

## ✨ Credits

- [TurtleBot4 Documentation](https://turtlebot.github.io/)
- [slam_toolbox](https://github.com/SteveMacenski/slam_toolbox)

---

## 📬 Contact

For any queries, reach out at: `your-email@example.com`

