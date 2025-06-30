# FPV Drone PCB Full PCB + Assembly - Work in Progress

A comprehensive open-source avionics ecosystem for FPV drones featuring a completed flight computer PCB along with in-development power distribution and electronic speed controller PCB. This project delivers an avionics stack for a custom drone with full schematic and PCB files available on KiCad 9.0.

## Overview

This project aims to create a FPV drone with a custom all-in-one (AIO) PCB that combines the flight controller, power distribution, and ESC functionality. Built around the STM32F411CEU6 microcontroller, this drone follows BetaFlight design requirements while providing a clean and efficient build.



## Hardware 

 **Integrated PCB Design**
  - Flight Controller: STM32F411CEU6 (ARM Cortex M4)
  - Power Distribution: High-current paths with filtering
  - ESC: BLHeli_S/BLHeli_32 compatible 4-in-1 design
  - OSD: Integrated MAX7456 chip for on-screen display

 **Connectivity**
  - All peripherals utilize SPI for high-speed sensor communication
  - UART port for external peripheral
  - Backup Coin Cell Battery Port
  - FTDI programming interface

<ins>**Flight Controller Board**</ins>
- STM32F411CEU6 microcontroller
- 12MHz external crystal oscillator
- MPU6500 gyroscope/accelerometer
- BMP280 barometer for altitude hold
- L86-M33 GPS for postional tracking
- SX 1276 LoRa 915MHz Transciever NiceRF Module
- Power options, LDO and External Power Board Connection

<ins>**Power and ESC Board**</ins>


**Power System**
- USB-C Power Option
- MP2393GTL-Z DC-DC buck converter for efficient power regulation
- Support for 3S-6S LiPo batteries (11.1V-22.2V)
- XT-60 connector for battery input
- 20A per motor capability (120A max total)
- Electric Speed Controller for four BLDC motors

**ESC (Electronic Speed Controller)**
- BLHeli_S/BLHeli_32 compatible
- 30-35A per motor capability
- Thermal management design
- Signal filtering for noise reduction
 




## Software Compatibility

This drone design is compatible with:
- BetaFlight (recommended for racing/freestyle)
- INAV (for GPS functions)
- Ardupilot (for autonomous capabilities)
- PX4 (for professional applications)

## Build Requirements

### Bill of Materials

| Component | Description | Specification |
|-----------|-------------|---------------|
| Frame | 3D printed carbon fiber | 5" freestyle/racing frame |
| Motors | Brushless | SpeedyBee 1800KV (recommended) |
| Battery | LiPo | 4S 1500mAh 100C (recommended) |
| Propellers | 5-inch | Matched to motor and frame |
| Camera | FPV | CCD or CMOS based on preference |
| Video Transmitter | 5.8GHz | Power output based on needs |
| Receiver | Radio control | Compatible with your transmitter |
| Antenna | 5.8GHz | Circular polarized |

### Tools
- Soldering iron and solder
- Heat shrink tubing
- Hex drivers/screwdrivers
- LiPo battery charger
- Multimeter
- KiCAD for PCB design modifications
- Zip ties
- Double-sided foam tape

### Electronics Knowledge
- Basic soldering skills
- Understanding of power systems
- Familiarity with microcontrollers
- Ability to flash firmware

## Calculations

### Power System
- Max Current = 4 motors × 30A = 120A
- Required C Rating = 120A / 1.5Ah = 80C minimum
- Flight time estimate = (1500mAh) ÷ (Average current draw) × 60 × 0.8

### Weight Budget
- Target all-up-weight: ~500g (5" freestyle quad)
- Battery weight: ~120-150g (4S 1500mAh)
- Component weight distribution accordingly

## Testing Procedures

1. Power system verification (voltage output, regulation)
2. Motor/ESC testing with servo tester
3. Sensor calibration and verification
4. Radio range and failsafe testing
5. Controlled hover tests
6. Full flight testing

## Media 
**Flight Computer Schematic**
![image](https://github.com/user-attachments/assets/66eaace1-5f99-4fdb-9aa4-7867878309cd)



**Flight Computer PCB**


![image](https://github.com/user-attachments/assets/25b10c26-9e5e-4a46-b159-e48ac772de75)


**Flight Computer 3D Model**

![image](https://github.com/user-attachments/assets/9c4938de-f330-492c-8345-230773f7fb7f)




## Collaboration

This project is in collaboration with Ammar Mahmood and esb8, All PCB designs, firmware modifications, and build documentation are developed jointly to ensure the highest quality and performance.

## License

This project is released under the MIT License. All design files, including schematics, PCB layouts, and firmware modifications are open source and available for personal and commercial use with attribution.

## Resources

- [BetaFlight Documentation](https://betaflight.com/docs/getting-started/installation)
- [STM32F4 Reference Manual](https://www.st.com/resource/en/reference_manual/rm0383-stm32f411xce-advanced-armbased-32bit-mcus-stmicroelectronics.pdf)
- [ESB8 GitHub Repository](https://github.com/esb8)
- [Ammar Github Repository](https://github.com/ammarjmahmood)
- [Project GitHub Repository](https://github.com/your-username/esb8-fpv-drone)

## Contributing

We welcome contributions to this project! If you have suggestions, bug reports, or want to contribute code, please:
1. Fork the repository
2. Create a feature branch
3. Submit a pull request

---
*This FPV drone project aims to combine and create a full documentation on the latest in drone technology with custom-designed electronics to create a high-performance, reliable platform for racing, freestyle, or aerial photography.*
