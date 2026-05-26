# Autonomous Mecanum-Wheel Robot

## 1. Introduction
This project focuses on designing and implementing an **autonomous mobile robot (AMR)** using **Mecanum wheels**, enabling omnidirectional movement suitable for narrow environments and warehouses.

The system integrates:  
- **ESP32** – Low-level motor control, encoder processing, and hardware communication. 
- **Raspberry Pi 4** – high-level processing, SLAM, and navigation algorithms  
- **YDLIDAR X3 Pro** – real-time environment scanning and mapping  

The robot is capable of **localization, mapping (SLAM), obstacle avoidance**, and **path planning**.

---

## 2. Hardware Requirements
- **ESP32 DevKit**  
- **Raspberry Pi 4 (4GB or 8GB RAM)**  
- **YDLIDAR X3 Pro**  
- **GA25 DC Motors with Encoders** (x4, with Mecanum wheels)  
- **Motor Drivers (L298N or equivalent, 4 channels)**  
- **12V Battery Pack**  
- **Frame & chassis with Mecanum wheels**
<!-- Row 1: 1 image -->
<p align="center">
  <img src="img/overview.png" width="60%">
</p>

<!-- Row 2: 2 images -->
<p align="center">
  <img src="img/floor1.png" width="45%">
  <img src="img/floor2.png" width="45%">
</p>

<!-- Row 3: 2 images -->
<p align="center">
  <img src="img/front.png" width="45%">
  <img src="img/right.png" width="45%">
</p>

---

## 3. Software Requirements
- **Ubuntu 20.04 / 22.04**  
- **ROS 2 Foxy / Humble**  
- **YDLIDAR X3 Pro**  
- **VS Code with PlatformIO extension** (for ESP32 firmware)  
- **Motor Drivers (L298N or equivalent, 4 channels)**  
- **SLAM Cartographer**  
- **Nav2 (Navigation2)**
- **YDLIDAR SDK**

---

## 4. Installation & Setup

### ESP32
1. Install [Arduino IDE](https://www.arduino.cc/en/software) or ESP-IDF.  
2. Flash motor control firmware (`esp32_motor_control.ino`).  
3. Connect encoders and motor drivers to ESP32.  

### Raspberry Pi 4
1. Install Ubuntu and ROS 2.  
2. Install LiDAR SDK:
3. Run the required file
```bash
ros2 launch motor_control kinematic.launch.py
ros2 launch motor_control serial_brigde.launch.py
ros2 launch ydlidar_ros2_driver ydlidar_launch.py
```

### Laptop
1. Install Ubuntu and ROS 2.
 ```bash
ros2 launch mecanum_joy mecanum_joy.launch.py
ros2 launch rf2o_laser_odometry rf2o_laser_odometry
ros2 launch robot_mapping cartographer.launch.py
ros2 launch robot_navigation navigation.launch.py
```
  
