# AquaNode

Smart aquarium monitoring platform powered by ESP32.

AquaNode is an embedded IoT system designed to monitor and automate aquarium conditions using an ESP32 microcontroller. It collects environmental data, controls equipment and uploads telemetry to a cloud database for dashboards and analytics.

---

## Features

- Real-time water temperature monitoring
- Automatic lighting schedule control
- Heater activity detection
- WiFi connectivity
- Cloud telemetry upload
- Optional microSD offline backup
- Fault-tolerant data buffering
- Expandable sensor architecture
- Low power embedded operation
- 24/7 autonomous monitoring

---

## Hardware

Current MVP hardware:

- ESP32 / ESP32 NodeMCU
- DS18B20 waterproof temperature sensor
- Relay module for lighting control
- Heater state detector
- Optional microSD module
- Power supply 5V

---

## Software Stack

- MicroPython
- HTTP / REST telemetry
- InfluxDB Cloud or compatible TSDB
- Grafana dashboards
- NTP time sync
- Local CSV backup (optional)

---

## Architecture

```text
Sensors / Actuators
       ↓
     ESP32
       ↓
 WiFi Network
       ↓
 Cloud Database
       ↓
 Dashboard / Analytics
