# Fingerprint-Based Attendance System

A WiFi-enabled biometric attendance system using the **Arduino UNO R4 WiFi**, **R307 fingerprint sensor**, and **0.96" OLED display**. This project logs attendance data by verifying fingerprints and sends the result to a local PHP-MySQL server hosted on XAMPP.

---

## Project Overview

This system automates attendance management by replacing manual processes with biometric verification. It provides real-time feedback via an OLED display and communicates with a local database through HTTP requests over WiFi.

---

## 🛠️ Hardware Components

| Component              | Description |
|------------------------|-------------|
| Arduino UNO R4 WiFi    | Main microcontroller with built-in WiFi (ESP32-S3 coprocessor) |
| R307 Fingerprint Sensor| Optical sensor used for fingerprint capture, matching, and storage |
| 0.96\" OLED Display     | Displays user messages (e.g. “Welcome”, “Goodbye”) via I2C |
| Jumper Wires & Breadboard | For connecting components during prototyping |
| XAMPP (PC)             | Hosts the local Apache + MySQL server and PHP scripts |

---

## 💻 Software Features

- Fingerprint **enrollment**, **matching**, and **deletion**
- **WiFi connectivity** and automatic reconnection logic
- Sends attendance data to a local **PHP server** via **HTTP GET**
- Stores and retrieves data from a **MySQL database**
- OLED visual feedback for enrollment, verification, and errors
- Server-based **mode switching** (Admin ↔ Attendance)
- Remote fingerprint ID management (via HTTP commands)

---

## 📚 Libraries Used

- [`WiFiS3`](https://www.arduino.cc/en/Reference/WiFiS3) — Connects to Wi-Fi using onboard ESP32-S3 chip  
- [`ArduinoHttpClient`](https://github.com/arduino-libraries/ArduinoHttpClient) — Sends HTTP GET requests  
- [`Adafruit_Fingerprint`](https://github.com/adafruit/Adafruit-Fingerprint-Sensor-Library) — Controls R307 sensor  
- [`Adafruit_GFX`](https://github.com/adafruit/Adafruit-GFX-Library) & [`Adafruit_SSD1306`](https://github.com/adafruit/Adafruit_SSD1306) — For OLED display rendering

---
