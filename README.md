# AquaNode

> Embedded IoT platform for intelligent aquarium monitoring, telemetry, and autonomous environmental control using ESP32.

![Platform](https://img.shields.io/badge/platform-ESP32-blue)
![Language](https://img.shields.io/badge/language-MicroPython-green)
![Status](https://img.shields.io/badge/status-active-success)
![License](https://img.shields.io/badge/license-MIT-lightgrey)

---

## Overview

AquaNode is a production-oriented embedded systems project focused on **real-time monitoring**, **fault tolerance**, and **cloud telemetry** for aquariums.

Built around an ESP32 microcontroller, the system continuously measures environmental variables, controls hardware peripherals, synchronizes with cloud infrastructure, and preserves operational continuity during connectivity failures.

This project combines principles from:

- Embedded Systems Engineering
- IoT Architecture
- Sensor Integration
- Edge Computing
- Reliability Engineering
- Telemetry Pipelines
- Real-Time Automation

---

## Why This Project Matters

Aquarium ecosystems are sensitive to small environmental changes. Temperature drift, lighting inconsistency, or heater malfunction can rapidly affect biological stability.

AquaNode was designed to solve these problems through:

- Continuous monitoring
- Automated control logic
- Historical data visibility
- Failure recovery mechanisms
- Low-cost hardware deployment
- Expandable modular architecture

---

## Core Features

### Environmental Monitoring

- Water temperature tracking using DS18B20
- Runtime state monitoring for heater activity
- Light schedule execution and state logging
- Device uptime and health metrics

### Embedded Control

- Automated relay control for lighting cycles
- Deterministic scheduling logic
- Boot-state recovery after power loss
- GPIO-based actuator management

### Reliability & Fault Tolerance

- WiFi auto-reconnection
- Cloud upload retry strategy
- Local microSD backup during outages
- Buffered telemetry queue
- Autonomous recovery after reboot

### Cloud Integration

- HTTP telemetry publishing
- InfluxDB-compatible time-series ingestion
- Grafana dashboards
- Historical analytics and trend visualization

---

## System Architecture

```text
+------------------+
| Sensors / Inputs |
| DS18B20          |
| Heater State     |
| Schedulers       |
+--------+---------+
         |
         v
+------------------+
| ESP32 Edge Node  |
| AquaNode Core    |
| MicroPython      |
+--------+---------+
         |
         +----------------------+
         |                      |
         v                      v
+------------------+   +------------------+
| Cloud Telemetry  |   | Local SD Backup  |
| InfluxDB         |   | CSV / Queue Log  |
+--------+---------+   +------------------+
         |
         v
+------------------+
| Dashboards       |
| Grafana          |
+------------------+
````

---

## Engineering Highlights

### Edge Resilience Design

If connectivity is lost:

* Monitoring continues uninterrupted
* Measurements are persisted locally
* Sync resumes automatically when network returns

### Separation of Concerns

Project modules are organized for maintainability:

```text
main.py         -> application loop
config.py       -> centralized parameters
sensors.py      -> hardware abstraction
scheduler.py    -> automation logic
telemetry.py    -> cloud communication
storage.py      -> SD persistence
network.py      -> WiFi / NTP handling
logger.py       -> diagnostics
```

### Production Mindset

The system was intentionally designed beyond a hobby prototype:

* Recoverable states
* Non-blocking retry logic
* Configurable deployment
* Replaceable infrastructure endpoints
* Long-running unattended operation

---

## Technology Stack

### Hardware

* ESP32
* DS18B20
* Relay module
* Optional microSD module

### Software

* MicroPython
* InfluxDB
* Grafana
* NTP time synchronization
* HTTP telemetry protocol

---

## Example Configuration

```python
WIFI_SSID = "network_name"
WIFI_PASSWORD = "password"

TEMP_PIN = 4
LIGHT_RELAY_PIN = 16

UPLOAD_INTERVAL_SEC = 30
TIMEZONE_OFFSET = -3

ENABLE_SD_BACKUP = True
ENABLE_HEATER_MONITOR = True
```

---

## Operational Workflow

1. Device boots and initializes hardware
2. Connects to WiFi
3. Synchronizes time via NTP
4. Reads sensors periodically
5. Executes automation schedules
6. Uploads metrics to cloud
7. Falls back to SD storage if offline
8. Recovers automatically after failures

---

## Example Metrics

```text
aquarium temperature_c=25.6
aquarium lights_on=1
aquarium heater_on=0
aquarium wifi_connected=1
```

---

## Roadmap

Planned future enhancements:

* pH monitoring
* Water level detection
* TDS / conductivity sensors
* Local web dashboard
* OTA firmware updates
* Push notifications
* Predictive anomaly detection
* Multi-tank support

---

## What This Demonstrates

This repository showcases hands-on ability in:

* Embedded firmware design
* Hardware/software integration
* IoT systems architecture
* Data pipeline thinking
* Reliability engineering
* Autonomous device logic
* Real-world problem solving
* Scalable modular code organization

---

AquaNode is not a tutorial clone or sample CRUD project.
It is a systems-oriented engineering build involving hardware constraints, networking instability, state recovery, telemetry, and autonomous runtime behavior.

That combination closely reflects real production environments in IoT and edge computing.

---



## Author

**Federico Trujillo** Computer Engineering Student  • Embedded Systems • IoT • Automation • Data Systems

