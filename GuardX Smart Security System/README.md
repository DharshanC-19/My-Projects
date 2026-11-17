# GUARDX-SMART-SECURITY-SYSTEM

GuardX Smart Security System is an Arduino-based security system that combines dual-password authentication, servo motor door locking, buzzer alerts, ESP32-CAM video monitoring, and email notifications.

## 📖 Overview

GuardX Smart Security System is designed to improve access control for homes, offices, and other facilities. The system uses an Arduino Uno, a 4×4 keypad, and an LCD display for password entry and user interaction.

It implements two security modes: General Mode and Master Mode. Under normal conditions, the user enters the General Password to unlock the door. The servo motors control the locking mechanism, and the door automatically locks again after 5 seconds.

After three consecutive incorrect password attempts, the system switches to Master Mode, activates the buzzer, and triggers the ESP32-CAM for video monitoring. The Master Password is used to reset the system and return it to General Mode. Email notifications provide security alerts and system reset information.

## ✨ Features

- Dual-Password Authentication
- General Mode and Master Mode
- 4×4 Keypad-Based Password Entry
- LCD Display for User Interaction
- Servo Motor-Based Door Locking
- Automatic Door Locking After 5 Seconds
- Buzzer Alert After Three Incorrect Attempts
- ESP32-CAM Video Monitoring
- Security Email Notification in Master Mode
- System Reset Email Notification

## 🛠️ Hardware Components

| Component | Quantity |
|---|---:|
| Arduino Uno | 1 |
| ESP32-CAM Module | 1 |
| 4×4 Matrix Keypad | 1 |
| 16×2 I2C LCD Display | 1 |
| Servo Motors | 2 |
| Buzzer | 1 |
| Power Supply | As Required |
| Jumper Wires | As Required |

## 💻 Software Requirements

- Arduino IDE
- Arduino C++
- Wire Library
- LiquidCrystal_I2C Library
- Keypad Library
- Servo Library

## 🔄 System Workflow

1. The user enters the password using the 4×4 keypad.
2. The Arduino Uno checks the entered password.
3. If the General Password is correct, the servo motors unlock the door.
4. The door automatically locks again after 5 seconds.
5. After three consecutive incorrect attempts, the system switches to Master Mode.
6. The buzzer is activated, and the ESP32-CAM is triggered for video monitoring.
7. A security email notification is generated.
8. The Master Password is used to reset the system and return it to General Mode.

## 📚 Applications

- Home Security
- Office Access Control
- Small-Scale Security Systems

## 👥 Team Members

- Dharshan C
- Praveen Kumar N
- Sridhar Srinivasan

**Department:** Electronics and Communication Engineering  
**College:** Kingston Engineering College
