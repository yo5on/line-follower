# High-Speed PID Line Follower Robot

A high-speed line follower robot built using an ESP32 NodeMCU and an 8-array IR sensor. The robot uses a Proportional-Integral-Derivative (PID) control algorithm to achieve smooth, responsive, and accurate line tracking at high speeds.

---

## Project Overview

This project implements a high-speed autonomous line-following robot using an ESP32 as the main controller.

An 8-array IR sensor continuously detects the position of the line. The ESP32 processes the sensor readings, calculates the tracking error, and uses a PID controller to dynamically adjust the speed of the two motors.

The system is designed to maintain stable tracking while handling curves and sharp turns at relatively high speeds.

The project provides practical experience with:

- Embedded systems
- PID control
- Sensor-based navigation
- Motor control
- Real-time data processing
- Autonomous robotics

---

## Project Images

| Robot | Chassis |
|-------|---------|
| ![](pic1.jpeg) | ![](chasis.jpeg) |

---

## Features

- PID-based line tracking
- High-speed operation
- ESP32-based control system
- 8-array IR sensor input
- Responsive correction for line deviations
- Support for sharp turns
- Adjustable PID parameters
- Analog sensor-based position detection
- Dual DC motor control

---

## Hardware Components

| Component | Quantity |
|-----------|----------|
| ESP32 NodeMCU | 1 |
| TB6612FNG Motor Driver | 1 |
| N20 Motors | 2 |
| 8-Array IR Sensor | 1 |
| Smart ELX Multiplexer | 1 |
| 3.7V Li-ion Battery | 2 |
| Buck Converter | 2 |
| Chassis | 1 |

---

## PID Configuration

The current PID parameters are:

```cpp
Kp = 65;
Ki = 0.003;
Kd = 18;
```

These parameters determine how aggressively the robot responds to deviations from the line.

The values may need to be adjusted depending on:

- Track surface
- Line width
- Sensor positioning
- Motor characteristics
- Battery voltage
- Desired operating speed

### PID Terms

| Parameter | Function |
|-----------|----------|
| Kp | Controls the response to the current error |
| Ki | Accounts for accumulated error over time |
| Kd | Predicts and reduces rapid changes in error |

---

## Wiring

The complete wiring diagram is provided below.

![Wiring Diagram](wiring.jpeg)

---

## Repository Structure

```text
line-follower/
│
├── code.ino
├── README.md
├── wiring.jpeg
├── chasis.jpeg
├── pic1.jpeg
├── pic2.jpeg
└── components/
```

---

## Getting Started

### Prerequisites

Before setting up the project, ensure that you have:

- Arduino IDE
- ESP32 board support package
- ESP32 NodeMCU
- Required sensors and motor components
- Appropriate power supply
- USB cable for programming

### Clone the Repository

```bash
git clone https://github.com/yo5on/line-follower.git
cd line-follower
```

### Open the Project

Open `code.ino` in the Arduino IDE.

### Install Required Software

Install the following through the Arduino IDE:

- ESP32 Board Package
- Wire Library

### Configure the ESP32

1. Connect the ESP32 to your computer.
2. Select the appropriate ESP32 board.
3. Select the correct COM port.
4. Verify the wiring connections.
5. Open `code.ino`.

### Upload the Code

Click **Upload** in the Arduino IDE and wait for the upload to complete.

After uploading, place the robot on the track and power the system.

---

## System Architecture

```text
8-Array IR Sensor
        |
        v
   Smart ELX
  Multiplexer
        |
        v
      ESP32
        |
        v
   PID Controller
        |
        v
 TB6612FNG Driver
      /     \
     v       v
 N20 Motor  N20 Motor
```

---

## Working Principle

1. The 8-array IR sensor continuously detects the line position.
2. Sensor readings are processed by the ESP32.
3. The robot calculates the deviation, or error, from the desired line position.
4. The PID controller calculates a correction value based on the current, accumulated, and rate of change of the error.
5. The correction is applied to the motor speeds.
6. The TB6612FNG motor driver controls the two N20 motors.
7. This process repeats continuously, allowing the robot to follow the track while correcting deviations in real time.

---

## PID Control Formula

```text
PID Output =
(Kp × Error) +
(Ki × Integral) +
(Kd × Derivative)
```

Where:

- **Error** represents the difference between the desired line position and the detected position.
- **Integral** represents the accumulated error over time.
- **Derivative** represents the rate of change of the error.
- **Kp, Ki, and Kd** determine the contribution of each PID term.

---

## Applications

This project can be used as a platform for experimenting with:

- Autonomous mobile robotics
- PID-based control systems
- Sensor-based navigation
- Real-time motor control
- Embedded systems
- Autonomous vehicle concepts
- Robotics competitions

---

## Future Improvements

Potential improvements include:

- Automatic PID parameter tuning
- Maze-solving algorithms
- Junction detection
- Bluetooth-based PID tuning
- OLED debugging and telemetry display
- Improved sensor calibration
- Adaptive speed control
- Advanced path-planning algorithms

---

## Technologies

| Category | Technology |
|----------|------------|
| Microcontroller | ESP32 NodeMCU |
| Programming | C/C++ |
| Development Environment | Arduino IDE |
| Sensor | 8-Array IR Sensor |
| Motor Driver | TB6612FNG |
| Motors | N20 DC Motors |
| Control Algorithm | PID |
| Multiplexer | Smart ELX Multiplexer |

---

## Author

**Yoson**

Computer Science student interested in AI/ML, robotics, embedded systems, and automation.

GitHub: https://github.com/yo5on

---

## License

This project is intended for educational and personal use. You are free to explore, modify, and extend the project for your own robotics and embedded systems experiments.

---

If you find this project useful, consider giving the repository a star.
