# 🛢️ Oil Tank IoT Monitor

This Arduino-based IoT project enables real-time monitoring of the volume and condition of a liquid fuel (e.g. heating oil) inside a storage tank. It combines ultrasonic level sensing, environmental temperature tracking, and time synchronization via NTP to deliver accurate fuel estimation, daily consumption logging, and visual alerts.

## 🎯 Project Goals

- 🧪 **Volume Calibration & Level Measurement**: Converts raw distance readings to precise oil volume through tank geometry and calibration.
- 📡 **Frequent Level Sampling**: Measures liquid level every 1.5–2 seconds to offer live monitoring of changes in tank fill level.
- 🌡️ **Environmental Temperature Sensing**: Measures ambient temperature near the tank to adjust oil volume via thermal expansion formula.
- 🚦 **Overflow/Low Level Alerts**: Notifies through LEDs when tank reaches critical low or high levels.
- 📈 **Daily Usage Logging**: At the end of each day, logs the consumed litres and average temperature for that day.
- 📤 **Wireless Report**: Sends a summary log (e.g. `14624_67_15`, meaning June 14th: 67L consumed, avg temp 15°C) via WiFi for remote availability.

## 🔧 Hardware & Components

- Arduino Nano 33 IoT Board
- HC-SR04 Ultrasonic Sensor
- TMP36 Analog Temperature Sensor
- 3 LEDs (Green, Red, Blue)
- WiFi network for NTP sync (no cloud platform used)

## 🧠 Technical Highlights

- ⏱️ **RTC synchronization** via NTPClient library
- 📏 **Thermal expansion formula** adjusts litre count (ΔV = β·ΔT·V₀)
- 💡 **LEDs** indicate fill level (above max, below min) & optimal temperature for selling
- 🔁 **Daily initialization/reset** at defined times (e.g., 06:59:59 and 19:52:59)
- 🧾 **Daily string logs**: Combine date, consumption, and average temperature

## 📂 File Overview

```
oil-tank-iot-monitor/
├── oil_tank_monitor.ino     # Arduino sketch
├── README.md                # Project description
```
