# Server - Fingerprint-based Attendance System

This folder contains the server-side scripts and database for handling fingerprint-based attendance via HTTP requests from an Arduino UNO R4 WiFi device.

---

## 📁 Overview

This backend is powered by **PHP + MySQL**, hosted locally using **XAMPP**, and designed to:

- Log fingerprint scan events (login/logout)
- Handle fingerprint enrollment and deletion
- Track user activity and generate reports
- Allow real-time mode switching between "attendance" and "enrollment"
- Communicate securely with the Arduino via GET requests
