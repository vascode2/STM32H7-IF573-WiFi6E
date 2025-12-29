# STM32H7 Wi-Fi 6E Integration (1.8V SDIO Mod)

**Enabling Wi-Fi 6E on the STM32H747I-DISCO by modifying the hardware for 1.8V SDIO signaling.**

![Project Status](https://img.shields.io/badge/Status-Finished-success)
![Hardware](https://img.shields.io/badge/Hardware-STM32H747I--DISCO-blue)
![Engineering](https://img.shields.io/badge/Mod-1.8V_Logic_Level-red)

## 🎯 Project Goal
The primary goal of this project was to bridge a modern **Wi-Fi 6E module (Sona IF573)** to a legacy **STM32H747I-DISCO** board.

**The Challenge:** The Sona IF573 utilizes an M.2 interface requiring **1.8V signaling** for high-speed SDIO communication. However, the STM32H747I-DISCO defaults to **3.3V** logic on its SD card slot and lacks a native M.2 interface.

**The Solution:** This project documents the precise **hardware modifications** (regulator bypass and pull-up resistor relocation) required to convert the host board's SDIO bus to 1.8V, enabling successful high-speed driver enumeration.

## 🛠️ Technical Achievements
* **Hardware Engineering:** Modifying PCB logic levels from 3.3V to 1.8V via manual "fly-wire" bypasses.
* **Interface Bridging:** Adapting M.2 E-Key to Micro-SD form factors.
* **Dual-Core Firmware:** Configuring FreeRTOS on the Cortex-M7 while managing the Cortex-M4 network coprocessor.
* **Driver Optimization:** Enabling `BLHS_SUPPORT` (Bus/Link High Speed) macros for optimized throughput.

## 📂 Documentation
The full application note is hosted in this repository and also published online. It covers hardware modifications, software setup, and dual-core flashing procedures.

### 🌐 [View the Official Published Guide](https://lairdcp.github.io/guides/IF573-STM32H747I-DISCO-docs/1.0/if573-stm32h747i-disco.html)

You can also view the local version in the `docs` folder:

### [👉 Read the Complete Integration Note](docs/if573-stm32h747i-disco.md)

* **Hardware Mod:** Step-by-step soldering guide for 1.8V logic levels.
* **Project Setup:** Importing the driver into STM32CubeIDE.
* **Dual-Core Flashing:** Correct sequence for programming the CM4 and CM7 cores.

## 📦 Resources
* **Source Code:** Derived from Infineon AIROC STM32 Expansion Pack v1.6.0
* **Hardware Used:** STM32H747I-DISCO, Ezurio Sona IF573 DVK, Micro-SD to M.2 Adapter.

---
*Disclaimer: This project involves soldering on development hardware. Proceed with caution.*
