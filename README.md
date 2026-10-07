# Robotics & Embedded Systems

I build robotics systems across embedded firmware and ROS 2, with a focus on
real-time control, hardware/software integration, system debugging and
real-vehicle validation.

## Focus

- **Embedded systems** — STM32, motor control, encoders, IMU, UART and low-level control
- **Robot system software** — ROS 2, Linux, odometry, TF, localization and navigation
- **System integration** — firmware-to-ROS communication, sensors, device management and bringup
- **Engineering debugging** — timing, performance, lifecycle, communication and hardware/software fault isolation
- **Real-world validation** — bench testing, vehicle testing, logs and reproducible engineering documentation

## Featured Project

### Greenhouse Mecanum Robot

**STM32F407 + Raspberry Pi 4 + ROS 2 Jazzy + Nav2 MPPI Omni**

A four-wheel mecanum mobile robot developed from low-level chassis control to
integrated autonomous navigation and real-vehicle validation.

Key engineering work:

- Implemented mecanum kinematics, wheel-speed closed-loop control, encoder feedback and IMU yaw processing on STM32F407
- Integrated STM32 chassis control with ROS 2 through a serial communication layer
- Built the odometry / TF / RPLIDAR / AMCL localization chain
- Integrated Nav2 MPPI with the Omni motion model for mecanum navigation
- Added velocity smoothing, collision monitoring and high-priority gamepad takeover
- Diagnosed Pi 4 overload, Nav2 lifecycle resets, yaw drift, USB device instability and camera-stream issues
- Integrated RS485 environmental sensing and IMX219 remote video monitoring
- Completed physical robot testing and engineering handover documentation

**Repository:**  
[greenhouse-mecanum-robot](https://github.com/jtvales2/greenhouse-mecanum-robot)

**Project evolution:**  
[Watch the development video](https://github.com/jtvales2/greenhouse-mecanum-robot/blob/main/media/greenhouse_robot_project_evolution.mp4)

## Technical Stack

```text
Embedded
├── C
├── STM32F407
├── STM32 HAL / CMSIS
├── STM32CubeMX
├── Keil MDK
├── Motor / Encoder Control
├── IMU Integration
└── UART / Modbus-RTU

Robotics
├── ROS 2 Jazzy
├── Nav2
├── MPPI
├── AMCL
├── TF / Odometry
├── RPLIDAR
└── Mecanum Drive

Systems
├── Linux / Ubuntu
├── Raspberry Pi
├── Git
├── systemd
└── Hardware / Software Integration
