#  Data Logger Simulations (Wokwi Platform)

This repository contains the complete simulation source code, circuit mapping, and comprehensive project reports.Due to the unavailability of physical hardware components, tasks were fully executed and validated using the cloud-based **Wokwi Simulation Platform**


## 📊 Task 3 — Data Logger: Sensor to SD Card / Serial Stream

### 📌 Project Overview
Collects real-time environmental metrics sequentially using a `DHT22` Temperature/Humidity sensor and an `LDR` Light sensor, pairs them with precise live timestamps from a `DS1307` Real-Time Clock (RTC) module, and streams them into a structured CSV format.

### 🔌 Circuit Mapping (Task 3)
* **DS1307 RTC:** SDA → Pin A4 | SCL → Pin A5 | VCC → 5V | GND → GND
* **DHT22 Sensor:** Data → Pin 2 | VCC → 5V | GND → GND
* **LDR Module:** Analog Output (AO) → Pin A0 | VCC → 5V | GND → GND

### 🔋 Engineering Core Analysis (Deliverables Summary)
* **Sampling Rate:** Configured optimally to mitigate flash memory fatigue (FAT corruption) since environmental parameters alter gradually over longer temporal horizons.
* **Power Optimization:** Detailed solutions include transitioning the microcontroller into deep `POWER_DOWN` sleep profiles and waking up via hardware interrupts driven by the RTC's square wave pin, alongside RAM buffering before executing high-current flash burst writes.

---

## 📂 Project Directory Breakdown
* `/Task3_Code.ino` : Sensor telemetric logging script creating raw data streams.
* `/log.csv` : Extracted live data file containing 100+ timestamped environmental entries.
* `/*.docx` : Comprehensive technical engineering reports embedding circuit designs and active execution validation benchmarks.
