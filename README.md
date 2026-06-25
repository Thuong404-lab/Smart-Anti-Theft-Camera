# 📷 Smart Anti-Theft Camera System (ESP32-CAM)

<p align="center">
  <img src="https://img.shields.io/badge/Hardware-ESP32--CAM-blue.svg" alt="ESP32-CAM">
  <img src="https://img.shields.io/badge/Platform-Arduino_IDE-00979D.svg?logo=arduino" alt="Arduino">
  <img src="https://img.shields.io/badge/Integration-Telegram_Bot-2CA5E0.svg?logo=telegram" alt="Telegram">
</p>

## 📖 Introduction
This project is a **Smart Anti-Theft Camera System** built on the **ESP32-CAM** platform. It integrates a PIR motion sensor, an onboard camera, a buzzer, and an LED to detect intrusions, trigger local alarms, and send real-time visual alerts to users via a Telegram Bot. It is a cost-effective, highly interactive security solution suitable for homes, small offices, and indoor surveillance.

## ✨ Features
- **Real-Time Motion Detection**: Uses a PIR sensor to accurately detect human movement.
- **Instant Telegram Alerts**: Sends a captured image and alert message directly to your Telegram app.
- **Local Alarm System**: Activates a buzzer for an audible warning and an LED for low-light image capturing.
- **Remote Control**: Fully manageable via Telegram Bot commands.
- **Cooldown Mechanism**: Prevents repeated alerts from the same continuous motion.

## 📋 Table of Contents
- [System Architecture](#-system-architecture)
- [Hardware Components](#-hardware-components)
- [Software Requirements](#-software-requirements)
- [Setup & Installation](#-setup--installation)
- [Usage & Telegram Commands](#-usage--telegram-commands)
- [Future Improvements](#-future-improvements)
- [References](#-references)

## 🏗 System Architecture
The ESP32-CAM serves as the core control unit. When the PIR sensor detects motion:
1. The local alarm (buzzer & LED) is activated.
2. The camera captures an image of the monitored area.
3. The image and alert are sent to the Telegram Bot via Wi-Fi.
4. The system enters a cooldown state to prevent spam.

*(See [System Block Diagram](https://drive.google.com/file/d/1__tAAGlWrXJMr0ntsjNUFES3sSAVlxoV/view?usp=sharing) and [Flowchart](https://drive.google.com/file/d/1acOeKzf9qMByz16G-erntNfSfpW0cNVL/view?usp=sharing))*

## 🛠 Hardware Components
- **ESP32-CAM**: Core processing, camera module, and Wi-Fi connectivity.
- **PIR Motion Sensor (HC-SR501)**: Detects infrared radiation from moving bodies.
- **Buzzer**: Emits an audible alarm.
- **LED**: Provides additional lighting for the camera in dark environments.
- **Breadboard & Jumper Wires**: For component assembly.
- *(Optional)* IR Remote & Receiver for manual control.

*(Circuit Diagram available [here](https://app.cirkitdesigner.com/project/5e94724d-4b43-47cc-8751-4914fec5c02a))*

## 💻 Software Requirements
- **Arduino IDE**: For developing and uploading the C/C++ code.
- **ESP32 Board Package**: Installed via Arduino Board Manager.
- **Telegram Application**: For receiving alerts and sending commands.

## 🚀 Setup & Installation

### 1. Hardware Assembly
Connect the components according to the circuit diagram. Ensure the ESP32-CAM has a stable power supply (5V/2A recommended) to prevent brownouts during camera operation and Wi-Fi transmission.

### 2. Telegram Bot Setup
1. Open Telegram and search for **BotFather**.
2. Send `/newbot` and follow instructions to create a new bot.
3. Save the provided **Bot Token**.
4. Search for your bot in Telegram and send a `/start` message.
5. Get your **Chat ID** (You can use bots like `IDBot` to find your chat ID).

### 3. Software Configuration
1. Open `iot_ver.cpp` in Arduino IDE.
2. Update the configuration variables:
   ```cpp
   const char* ssid = "YOUR_WIFI_SSID";
   const char* password = "YOUR_WIFI_PASSWORD";
   String BOT_TOKEN = "YOUR_TELEGRAM_BOT_TOKEN";
   String CHAT_ID = "YOUR_CHAT_ID";
   ```
3. Select the **AI Thinker ESP32-CAM** board in Arduino IDE.
4. Compile and upload the code using an FTDI programmer.

*(Full source code is available [here](https://drive.google.com/drive/folders/1x-5Q1lwMtyaKwiBAzDIcapZwX5-3mXSp))*

## 📱 Usage & Telegram Commands
Once powered on, the system connects to Wi-Fi and begins monitoring. You can use the following commands in your Telegram Bot:
- `/start` - Check if the system is online.
- `/photo` - Request an instant photo capture.
- `/alarm_on` - Enable the alarm system.
- `/alarm_off` - Disable the alarm system.
- `/led_on` - Turn on the LED light manually.
- `/led_off` - Turn off the LED light.

*(See the Demo Video [here](https://drive.google.com/drive/folders/1xWWjPgqnMlk7wSHBefq4t83yAGc1cR--?usp=sharing))*

## 🚀 Future Improvements
- **AI Integration**: Implement human detection to reduce false alarms triggered by pets.
- **Battery Backup**: Add a Li-Po battery or solar panel for continuous operation during outages.
- **Smart Home Integration**: Connect with platforms like Home Assistant or Blynk.

## 📚 References
- [Esp32-Cam-PIR-Telegram](https://github.com/LucaTomei/Esp32-Cam-PIR-Telegram)
- [Home-Security-System-using-ESP32CAM](https://github.com/make2explore/Home-Security-System-using-ESP32CAM-and-Telegram)

---
*Created by SE1912_Group3_IOT102 Team*
