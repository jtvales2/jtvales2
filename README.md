# Robotics & Embedded Systems

I build robotics and embedded systems across STM32 firmware and ROS 2, with a focus on real-time control, sensor integration, system debugging, and hands-on testing. My projects span both self-developed quadrotor flight-control firmware and mobile robot systems.

## Focus

- **Embedded systems** — STM32, interrupt-driven acquisition, SPI DMA, UART, motor control, encoders and IMU
- **Robot system software** — ROS 2, Linux, odometry, TF, localization and navigation
- **System integration** — firmware-to-ROS communication, sensors, device management and bringup
- **Engineering debugging** — timing, data freshness, performance, lifecycle and hardware/software fault isolation
- **Real-world validation** — bench testing, flight and vehicle testing, logs and development records

## Featured Projects

### STM32 Quadrotor Flight Controller

**STM32F407 + BMI088 + MS5611 | SPI DMA · Mahony · Cascaded Control**

I developed a quadrotor flight-controller firmware project to understand and implement the full embedded control chain—from sensor interrupts and data acquisition to attitude estimation, closed-loop control, motor output and fault handling.

Key engineering work:

- Designed asynchronous BMI088 accelerometer/gyroscope acquisition using DRDY interrupts and SPI DMA
- Used timestamped ring buffers, sample pairing and freshness checks to manage timing between acquisition and estimation
- Implemented a Mahony-based quaternion attitude estimator and integrated roll/pitch cascaded control, yaw control and motor mixing
- Built MS5611 barometer interfaces and altitude-related control logic
- Added DMA timeout recovery, backlog handling, arming guards and failsafe paths
- Recorded real bench tuning traces and indoor/outdoor prototype flight tests

**[View source code, system architecture and full project portfolio](https://github.com/jtvales2/stm32-flight-controller)**

[Outdoor flight test](https://github.com/jtvales2/stm32-flight-controller/blob/main/media/flight/outdoor-test.mp4) · [Indoor flight test](https://github.com/jtvales2/stm32-flight-controller/blob/main/media/flight/indoor-test.mp4) · [Bench test](https://github.com/jtvales2/stm32-flight-controller/blob/main/media/bench/bench-test.mp4)

<a href="https://github.com/jtvales2/stm32-flight-controller/blob/main/media/flight/outdoor-test.mp4"><img src="https://raw.githubusercontent.com/jtvales2/stm32-flight-controller/main/media/flight/outdoor-cover.jpg" width="420" alt="Outdoor flight test of my STM32 quadrotor prototype" /></a>

*The videos document early prototype tests rather than quantified flight-performance benchmarks.*

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
├── Interrupts / SPI DMA / UART
├── IMU / Timestamped Sensor Data
├── Attitude Estimation / Cascaded Control
├── Motor / Encoder Control
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
```
