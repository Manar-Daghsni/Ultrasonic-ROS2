# Ultrasonic Sensor Array – ROS2 Distance Scanning

[![ROS2](https://img.shields.io/badge/ROS2-Jazzy-orange?style=for-the-badge)](https://docs.ros.org/en/jazzy/)


---

## 🚀 Overview

This project integrates an **Ultrasonic Sensor Array** with **ROS2 Jazzy** on a Raspberry Pi 5 and Arduino Uno.  

It provides:

- 🔹 Real-time distance measurement from multiple ultrasonic sensors  
- 🔹 ROS2 topic publishing for easy integration into robotics projects  
- 🔹 Expansion-ready design for obstacle detection, mapping, or navigation  



---

## 🗂️ Project Structure

```
ultrasonic/
├── ultrasonic_sensors/       # ROS2 package for Pi5
│   ├── launch/               # Launch files
│   ├── src/                  # ROS2 nodes
│   └── test/                 # Unit tests
├── UltrasonicSensor.h        # Arduino header for sensor communication
├── README.md                 # This file

```

---

## ⚙️ Prerequisites

- Raspberry Pi 5 with Ubuntu 24.04  
- ROS2 Jazzy installed  
- Arduino Uno with `UltrasonicSensor.h` sketch uploaded  
- `colcon` build tool installed on the Pi  

---

## 🛠️ Setup Instructions

1. **Clone the repository:**
```bash
git clone https://github.com/<your-username>/Ultrasonic-ROS2.git
cd Ultrasonic-ROS2
```

2. **Build the ROS2 workspace:**
```bash
colcon build
source install/setup.bash
```

3. **Connect Arduino Uno** with the ultrasonic sensor array via USB .

---

## ▶️ Running the Project

1. **Launch the ROS2 node:**
```bash
ros2 launch ultrasonic_sensors ultrasonic_launch.py
```

2. **View sensor data:**
```bash
ros2 topic echo /ultrasonic_echo
```

> The `/ultrasonic_echo` topic publishes distance values from all sensors in real-time.

---

## 📡 Arduino Integration

- Include `UltrasonicSensor.h` in Arduino sketch  
- Connect each ultrasonic sensor to the pins defined in sketch  
- Arduino sends distance data via serial to the Raspberry Pi  


---

## 💡 Notes

- Topic and node names can be customized in the launch file  
- Designed to scale to additional sensors or integrated into larger ROS2 systems




---

## 🔗 References

- [ROS2 Jazzy Documentation](https://docs.ros.org/en/jazzy/)  
- [Arduino Ultrasonic Sensor Tutorials](https://www.arduino.cc/en/Tutorial/UltrasonicSensor)  
- [Serial Communication Arduino ↔ Raspberry Pi](https://www.raspberrypi.org/documentation/usage/gpio/)

