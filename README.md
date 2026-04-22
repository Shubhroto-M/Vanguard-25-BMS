# 🐉 VANGUARD 25: Industrial-Grade 5S Battery Management System

![Status: V1.0 Complete](https://img.shields.io/badge/Status-V1.0_Complete-success)
![Platform: KiCad 9.0](https://img.shields.io/badge/Platform-KiCad_7.0-blue)
![License: MIT](https://img.shields.io/badge/License-MIT-green)

> **Vanguard 25** is an open-source, high-current (20A) Battery Management System designed with strict, aerospace-style redundant safety architectures. It is built to handle massive current dumps while protecting lithium-ion chemistry from catastrophic failure modes.

*(Insert your best 3D Render of the top and bottom of the board here)*

## ⚡ Core Specifications
* **Architecture:** 5S (Configurable down to 3S/4S via hardware solder jumpers).
* **Operating Voltage:** 21V Max.
* **Current Capacity:** 25A Continuous / 45A Peak Over-current.
* **Balancing:** 150mA active hardware balancing per cell.
* **PCB Specs:** 2-Layer, standard 1oz/2oz copper, designed for Matte Black Solder Mask with ENIG (Gold) plating.

## 🛡️ Dual-Tier Safety Architecture
Unlike standard hobbyist BMS boards that rely on a single point of failure, Vanguard 25 implements a strictly hardware-based, dual-redundant safety net. **There is zero firmware to crash.**

1. **Primary Logic (BM3451):** Handles standard cell balancing, over-charge (OVP), over-discharge (UVP), and over-current protection.
2. **Redundant Failsafe (BQ771807):** The "Paranoia Chip." Runs on a completely independent internal voltage reference. If a cell hits a critical **4.5V hard cutoff**, it bypasses the main logic entirely.
3. **Hardware Kill Switch (Dexerials SKF-2045):** If the BQ771807 trips, it fires a voltage into the heater element of this chemical fuse, physically and permanently severing the main power line to prevent thermal runaway.

## 📐 Layout & Routing Strategy
* **Total Signal Isolation:** Massive, high-current copper polygons are restricted to the outer edges of the board. The sensitive analog measurement lines and logic ICs are grouped in a protected central island to prevent EMI and switching noise interference.
* **Thermal Management:** The parallel MOSFET bridge features aggressive thermal via stitching, allowing the internal and bottom copper planes to act as massive passive heatsinks during 25A continuous loads.
* **DRC Cleared:** 0 Errors, 0 Warnings under strict clearance constraints.

## 📁 Repository Contents
* `/KiCad_Project` - Full schematic and PCB layout files.
* `/Gerbers` - Production-ready manufacturing files.
* `/3D_Models` - STEP files for mechanical enclosure integration.

## ⚠️ DANGER & DISCLAIMER
**Lithium-Ion batteries contain massive amounts of energy and can cause fires, explosions, and severe injury if mishandled.**
This repository is provided as an open-source portfolio project and educational reference. It has not been tested by UL, CE, or any other regulatory body. If you choose to fabricate this board, populate the components, and connect it to live lithium cells, you do so entirely at your own risk. The designer takes absolutely zero responsibility for any damage to property, equipment, or persons. 

---
*Designed in Bengaluru.*
