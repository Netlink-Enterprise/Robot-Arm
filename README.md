Markdown

# Mini Servo Robotic Arm Firmware & Control System

A clean, modular control and automation script package designed for multi-axis mini servo robotic arms (compatible with SG90 / MG996R servos and microcontroller setups).

---

## 🚀 System Architecture

```text
[ Host Device / Python Script ] 
       │ (Serial / USB)
       ▼
[ Arduino / Microcontroller ] ──► [ PWM Servos (Base, Shoulder, Elbow, Gripper) ]

🛠️ Hardware Requirements
Component	Description
Microcontroller / SBC	Arduino Uno / Nano or Raspberry Pi
Actuators	4x to 6x Mini Servos (SG90 or high-torque variants)
Power Supply	External 5V DC Power Source (Isolated from microcontroller logic pins to prevent voltage drops)
Chassis	3D-printed robotic arm mechanical assembly
📂 Repository Structure
Plaintext

├── firmware/
│   └── arduino_servo_control.ino   # Arduino sketch for direct serial-controlled positioning
├── software/
│   └── python_pca9685/             # Python script for I2C / PCA9685 driver boards
└── README.md

⚙️ Pinout Configuration (Arduino Direct Control)
Joint / Actuator	Arduino Digital Pin
Base Servo	Pin 3
Shoulder Servo	Pin 5
Elbow Servo	Pin 6
Gripper Servo	Pin 9
📥 Installation & Quick Start
1. Arduino Firmware Setup

    Open the Arduino IDE.

    Load the sketch from firmware/arduino_servo_control.ino.

    Select your board and port, then upload the code to your microcontroller.

    Open the Serial Monitor at a baud rate of 115200.

2. Sending Serial Commands

You can manually command individual joints in real-time by sending single-character commands followed by target angles:

    B90 — Move Base to 90 degrees

    S45 — Move Shoulder to 45 degrees

    E120 — Move Elbow to 120 degrees

    G30 — Move Gripper to 30 degrees

📜 License

Distributed under the MIT License. Feel free to modify, fork, and adapt for your own builds.
