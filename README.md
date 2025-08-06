# Model Rocketry Flight Computer and Embedded Patch Antenna – Full PCB + Assembly

An open-source avionics system developed for **model rocketry** applications by the [Metropolitain Aerospace Rocket Society at Toronto Metropolitan University (MARSTMU)](https://marstmu.com/). Originally designed for FPV drones, this project has been adapted into a **flight computer** supporting GPS, sensor fusion, data logging, and telemetry, all within a compact, custom PCB. This board also features a **custom microstrip antenna** designed by [Javezki](https://github.com/Javezki). All schematics and KiCad 9.0 PCB design files are openly available.

---

## Overview

This project delivers a robust and flexible **flight computer** for **high-power G-80 model rockets**, built on the STM32F411CEU6 microcontroller. It provides modular avionics functionality—combining flight control, telemetry, power management rated for 1S-2S LiPo, and sensor integration—making it suitable for in-flight data acquisition, staging logic, and recovery system deployment.

---

## Hardware Overview

### **Integrated Flight Computer Design**
- **Flight Computer**: STM32F411CEU6 (ARM Cortex M4)
- **Power Regulation**: High-efficiency DC-DC converters (1S LiPo)
- **Telemetry**: Long-range LoRa communication
- **Sensor Suite**: Altitude, attitude, temperature, and pressure sensing

### **Interfaces & Expansion**
- SPI-connected sensor peripherals
- USB-C programming and data offloading
- JTAG/SWD debug support
- UART/FTDI interface for external modules
- Coin cell backup power for RTC
- GPS module for position logging

---

## Flight Computer Board Features

- **MCU**: STM32F411CEU6 (100MHz ARM Cortex-M4)
- **Clock Source**: 12MHz external crystal
- **IMU**: ICM-42605 (gyro + accel)
- **Barometer**: BMP280 for altitude tracking
- **GNSS**: L86-M33 GPS module (GLONASS+GPS)
- **Telemetry**: SX1276 LoRa 915MHz transceiver (NiceRF)
- **Power**: USB-C input, LDOs, and external 3.3V support

---

## Power System (Planned for Rocket Integration)

- SWD Flash for in-field reprogramming
- High-efficiency DC-DC converters
- Battery support: 1-2S LiPo or custom packs
- Regulated 3.3V rail for sensitive components
- XT60 or JST input connector options

---

## Software Compatibility

- **BetaFlight** (legacy; for IMU prototyping)
- **Custom C/C++ Firmware** (recommended for real-time rocketry logic)

---

## Bill of Materials (Key Components)

| Component         | Description                         | Specification                             |
|------------------|-------------------------------------|-------------------------------------------|
| Frame            | Enclosure/Avionics Bay              | Custom 3D-printed or machined             |
| MCU              | STM32F411CEU6                       | ARM Cortex M4 100MHz                      |
| GPS              | L86-M33                             | GNSS Positioning                          |
| IMU              | ICM-42605                           | 6DOF motion tracking                      |
| Barometer        | BMP280                              | Pressure & altitude sensor                |
| Radio            | SX1276 LoRa                         | 915MHz telemetry                          |
| Battery          | LiPo / Rocket battery pack          | 1S–2S supported via DC regulation         |
| Connectors       | USB-C, JST, XT60                    | Power + Programming                       |
| Antenna          | SMA 915MHz                          | Half-dipole LoRa                          |

---

## Tools & Assembly Requirements

- Soldering iron + fine solder
- Heat shrink tubing
- Multimeter & continuity tester
- LiPo battery charger (if applicable)
- Debug tools: ST-Link V2 / J-Link
- KiCad (PCB design and modification)
- Screws, standoffs, foam tape, zip ties

---

## Required Knowledge

- Soldering and PCB assembly
- STM32 microcontroller basics
- Familiarity with LoRa/telemetry systems
- Firmware flashing and serial debugging
- Understanding model rocketry avionics architecture

---

## Calculations

### Altimeter/Flight Timing Logic
- Barometer resolution: ±1 meter (BMP280)
- GPS fix interval: 1Hz–10Hz (L86-M33)
- IMU update: Up to 1kHz via SPI

### Power Budget
- MCU current draw: ~50mA
- LoRa TX Peak: ~120mA
- Sensors + GPS: ~30–50mA
- Total ~200–250mA @ 3.3V (0.7–1W typical)

---

## Testing & Validation

1. Flash microcontroller via SWD
2. USB-C serial communication verification
3. IMU and GPS data output test
4. Barometer altitude validation
5. LoRa telemetry range and signal integrity
6. Full ground simulation test (power cycling, resets)
7. Field tests (static fire or live launch)

---

## Media

### Flight Computer – 3D Model

<img width="1149" height="898" alt="image" src="https://github.com/user-attachments/assets/67c6b6bd-6ebe-4df5-8a24-93755f462e03" />

---

## Collaboration


This system is being developed by **Evan Bhogal** and **Javezki** for the **Metropolitan Aerospace Rocketry Society at TMU** for use in high-power rocketry and avionics research.

---

## License

Released under the **MIT License**. All PCB files, schematics, and firmware modifications are open source and may be reused and modified with appropriate attribution.

---

## Resources

- [MARSTMU](https://marstmu.com)
- [Javezki Github](https://github.com/Javezki)
- [ESB8 GitHub](https://github.com/esb8)
  
---


*This avionics platform bridges the gap between custom hardware and flight-ready model rocketry systems, enabling high-altitude data logging, telemetry, and robust in-flight control capabilities.*
