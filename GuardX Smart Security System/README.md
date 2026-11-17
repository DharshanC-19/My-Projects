# GUARDX – Smart Security System 🔐

An Arduino-based smart door lock system featuring dual-password authentication, automatic door control, buzzer alerts, and IoT connectivity.

## 📌 Project Overview

**GuardX Smart Security System** is an embedded systems and IoT-based security project designed to improve access control and entrance monitoring.

The system uses an Arduino Uno as the main controller, a 4×4 keypad for password entry, an LCD for user interaction, and servo motors for door locking and unlocking.

It implements a dual-password authentication mechanism with General Mode and Master Mode. After three consecutive incorrect password attempts, the system enters Master Mode and activates an audible alarm.

The project also explores wireless monitoring and IoT-based data communication.

## ✨ Key Features

- **Dual Password Authentication:** Supports general and master password access.
- **Automatic Door Control:** Uses servo motors to lock and unlock the door.
- **LCD User Interface:** Displays system status and password-entry messages.
- **Unauthorized Access Detection:** Detects three consecutive incorrect password attempts.
- **Master Mode:** Activates a security lockout condition after repeated incorrect attempts.
- **Buzzer Alert:** Produces an audible alarm during Master Mode.
- **ESP Trigger Output:** Generates a trigger signal when the system enters Master Mode.
- **IoT Connectivity:** Includes an ESP8266-based sketch for uploading sensor data to ThingSpeak.
- **Camera Monitoring Concept:** ESP32-CAM-based entrance monitoring is described in the project report.

## ⚙️ Hardware Components

| Component | Purpose |
|---|---|
| Arduino Uno | Main control unit |
| 4×4 Keypad | Password input |
| 16×2 I2C LCD | System status display |
| Servo Motors (2) | Door locking and unlocking |
| Buzzer | Security alarm |
| ESP8266 | Wi-Fi and ThingSpeak communication |
| ESP32-CAM | Camera monitoring described in the project report |
| Power Supply | Powers the system components |

## 💻 Software and Technologies

- Arduino IDE
- Embedded C/C++ (Arduino programming)
- ESP8266 Wi-Fi Communication
- ThingSpeak IoT Platform

### Libraries Used

**Arduino Uno code:**
- `Wire.h`
- `LiquidCrystal_I2C.h`
- `Keypad.h`
- `Servo.h`

**ESP8266 code:**
- `ESP8266WiFi.h`
- `ThingSpeak.h`

## 🔄 Working Principle

### 1. General Mode

- The system starts in a locked condition.
- The user enters the general password through the keypad.
- The LCD displays the access status.
- If the password is correct, the servo motors unlock the door.
- After five seconds, the door automatically returns to the locked position.

### 2. Incorrect Password Detection

- Each incorrect password increases the failure counter.
- The system allows three incorrect attempts.
- After the third incorrect attempt, it switches to Master Mode.
- The buzzer activates to indicate an unauthorized access condition.
- A trigger signal is generated at the ESP trigger output.

### 3. Master Mode

- Normal password access is disabled.
- Only the master password can reset the system.
- After successful master authentication, the system returns to General Mode.
- The failure counter is reset.

### 4. IoT Data Communication

The supplied ESP8266 sketch receives six comma-separated integer values through serial communication and uploads them to ThingSpeak.

| ThingSpeak Field | Parameter |
|---|---|
| Field 1 | Water Level |
| Field 2 | Temperature |
| Field 3 | Humidity |
| Field 4 | Soil Moisture |
| Field 5 | Rain |
| Field 6 | LDR |

The ESP8266 sketch uses Wi-Fi connectivity to transmit the received values to the configured ThingSpeak channel.

## 🔌 Arduino Uno Pin Configuration

| Component | Arduino Uno Pin |
|---|---|
| Keypad Row 1 | 9 |
| Keypad Row 2 | 8 |
| Keypad Row 3 | 7 |
| Keypad Row 4 | 6 |
| Keypad Column 1 | 5 |
| Keypad Column 2 | 4 |
| Keypad Column 3 | 3 |
| Keypad Column 4 | 2 |
| Buzzer | 12 |
| ESP Trigger | 11 |
| Servo Motor 1 | 10 |
| Servo Motor 2 | A0 |
| LCD | I2C (Address: 0x27) |

## 📂 Project Structure

```text
GUARDX-Smart-Security-System/
│
├── README.md
│
├── Arduino_Uno/
│   └── GuardX_Uno.ino
│
├── ESP8266_ThingSpeak/
│   └── ThingSpeak_Upload.ino
│
└── assets/
    ├── images/
    │   ├── guardx-prototype.jpg
    │   └── hardware-setup.jpg
    │
    └── videos/
        └── guardx-demo.mp4
```

*The filenames above are suggested names. Update them to match the files you upload.*

## 📸 Project Images

### Hardware Implementation

![GuardX Prototype](assets/images/guardx-prototype.jpg)

### Hardware Setup

![Hardware Setup](assets/images/hardware-setup.jpg)

## 🎥 Project Demonstration

[▶ Watch GuardX Project Demonstration](assets/videos/guardx-demo.mp4)

## 🚀 Getting Started

1. Install the Arduino IDE.
2. Connect the required hardware components according to the pin configuration.
3. Install the required Arduino libraries.
4. Open and upload the Arduino Uno sketch.
5. Configure the ESP8266 Wi-Fi credentials and ThingSpeak channel details.
6. Upload the ESP8266 sketch using the appropriate ESP8266 board configuration.
7. Test password authentication, door control, alarm activation, and IoT data transmission.

**Important:** Keep Wi-Fi credentials and ThingSpeak API keys private. Do not publish them in your public repository.

## 📝 Implementation Notes

The supplied Arduino Uno sketch implements keypad authentication, LCD display, servo-based door control, buzzer alerts, and the ESP trigger output.

The supplied ESP8266 sketch implements serial sensor-data reception and ThingSpeak uploads.

The two supplied sketches do not yet show a complete communication link between the Arduino Uno and ESP8266. The Uno sketch does not transmit the six sensor values over serial, and the ESP8266 sketch does not read the trigger pin. The camera-streaming and email-alert functionality described in the project report also requires its corresponding camera/alert firmware.

## 👨‍💻 Project Team

- **Dharshan C**
- **Praveen Kumar N**
- **Sridhar Srinivasan**

**Institution:** Kingston Engineering College, Vellore  
**Department:** Electronics and Communication Engineering  
**Project Domain:** Embedded Systems and Internet of Things (IoT)  
**Academic Year:** 2025–2026

---

⭐ *GuardX demonstrates the application of embedded systems, password-based access control, microcontroller interfacing, and IoT technologies in a smart security application.*