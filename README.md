# ESP32-Smart-Relay: Open-Source Smart Relay Module
> A compact, production-ready 220V AC smart plug relay module built around the ESP32-C3, featuring full galvanic isolation, integrated AC-DC conversion, and exposed UART programming pins.
> 
## ⚡ Overview
This project is an open-source hardware design for a 10A Wi-Fi/Bluetooth smart relay. It is designed to sit between mains power and everyday appliances (lamps, fans, heaters), allowing for local or cloud-based smart home control.
Unlike many commercial closed-source smart plugs, this board exposes a standard 6-pin UART header, making it trivially easy to flash with custom firmware like **ESPHome**, **Tasmota**, or your own custom Arduino/C++ code.
## 🛠️ Hardware Features
 * **Microcontroller:** ESP32-C3-WROOM-02-H4 (RISC-V, Wi-Fi 4, Bluetooth 5 LE).
 * **Power Supply:** Onboard Hi-Link HLK-PM01 5V step-down module with an AMS1117 3.3V LDO for clean logic power.
 * **Galvanic Isolation:** The low-voltage ESP32 logic is physically and electrically isolated from the high-voltage relay coil using a **PC817 Optocoupler**.
 * **Switching Capacity:** 10A @ 250V AC Mechanical Relay (Songle SRD-05VDC), capable of switching up to 2200W.
 * **Safety First:** Includes a 10A slow-blow inline fuse, a Metal Oxide Varistor (MOV) for surge protection, and strict PCB creepage/clearance routing.
 * **Developer Friendly:** Dedicated 6-pin 2.54mm pitch programming header (3V3, GND, TX, RX, IO9/BOOT, EN/RESET).
## ⚠️ DANGER: HIGH VOLTAGE WARNING
**This project involves working with 220V-240V AC Mains Electricity.**
Mains voltage is lethal and can cause serious injury, death, or fire if mishandled. This repository is provided for educational and prototyping purposes only.
 * Never touch the PCB while it is connected to wall power.
 * Ensure your PCB manufacturer properly mills the isolation slots between the high-voltage and low-voltage sections.
 * Always house the final board in a non-conductive, fire-retardant enclosure.
## 🗜️ Flashing the ESP32-C3
To flash custom firmware (like ESPHome):
 1. Connect a 3.3V FTDI / USB-to-Serial programmer to the UART header.
   * *Note: Programmer TX goes to Board RX (Pin 11). Programmer RX goes to Board TX (Pin 12).*
 2. Do **NOT** connect AC mains power while the FTDI is plugged in. Power the board via the 3.3V pin on the header.
 3. To enter flash mode, hold IO9 to GND, briefly pulse EN to GND, then release IO9.
## 📁 Repository Contents
 * /Hardware - KiCad / EDA schematic and PCB layout files.
 * /Firmware - Example Arduino sketches and ESPHome .yaml configuration files.
 * /Enclosure - (Optional) 3D printable STL files for the housing.
