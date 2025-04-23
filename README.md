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

## 🖥️ Server Setup (XAMPP)

1. Install [XAMPP](https://www.apachefriends.org/index.html)
2. Start **Apache** and **MySQL** modules.
3. Import the `biometricattendance.sql` file via **phpMyAdmin**
4. Place PHP files (`getdata.php`, etc.) in:
C:\xampp\htdocs\biometricattendancev2\
5. Make sure the device and PC are on the same Wi-Fi network.

---

## 🔌 Wiring Diagram

| Fingerprint Sensor Pin | Arduino UNO R4 Pin | Description    |
|------------------------|--------------------|----------------|
| TX                     | RX (Serial1 RX)    | Sensor to Board |
| RX                     | TX (Serial1 TX)    | Board to Sensor |
| VCC                    | 5V                 | Power supply    |
| GND                    | GND                | Ground          |

| OLED Pin | Arduino UNO R4 Pin | Description     |
|----------|--------------------|-----------------|
| SDA      | SDA (A4)           | Data Line       |
| SCL      | SCL (A5)           | Clock Line      |
| VCC      | 3.3V or 5V         | Power supply    |
| GND      | GND                | Ground          |

---

## 🧠 Functional Overview

- Enroll a new fingerprint via server trigger
- Store fingerprint model with unique ID
- Authenticate fingerprint on scan and identify user
- Send data to server to mark **login** or **logout**
- OLED provides feedback: scan success, user status, etc.

---

## 💡 Inspiration

This project was inspired by [this video by Arnov Sharma (Electronic Clinic)](https://www.youtube.com/watch?v=4pQtER8PShw&t=506s), which demonstrated how to create a fingerprint attendance system using an ESP32 and PHP backend.

I extended the concept by:
- Rebuilding it with the **Arduino UNO R4 WiFi** for better compatibility and stability.
- Designing a more modular and scalable codebase.
- Implementing a cleaner OLED UI and Wi-Fi management logic.
- Structuring the backend with a richer PHP interface and database management.

Big thanks to Arnov Sharma and the maker community for sharing such great tutorials!

---

## 🧑‍💻 Author

**Esosa M. Johnson Ikponmwosa**
